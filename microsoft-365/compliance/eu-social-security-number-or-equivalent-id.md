---
title: EU-Sozialversicherungsnummer oder gleichwertige ID
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn Sie die Sozialversicherungsnummer der EU oder einen entsprechenden ID-vertraulichen Informationstyp ermittelt. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: 1f2d1d9c61f27fb47b0c7ac0ce544b17175d4254
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "41591226"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="42525-104">EU-Sozialversicherungsnummer oder gleichwertige ID</span><span class="sxs-lookup"><span data-stu-id="42525-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="42525-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn Sie den Typ der EU-Sozialversicherungsnummer (SSN) oder einen äquivalenten ID-vertraulichen Informationstyp erkennt.</span><span class="sxs-lookup"><span data-stu-id="42525-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="42525-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="42525-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="42525-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="42525-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="42525-108">Format</span><span class="sxs-lookup"><span data-stu-id="42525-108">Format</span></span>

<span data-ttu-id="42525-109">10 Ziffern im angegebenen Format</span><span class="sxs-lookup"><span data-stu-id="42525-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42525-110">Muster</span><span class="sxs-lookup"><span data-stu-id="42525-110">Pattern</span></span>

<span data-ttu-id="42525-111">10 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="42525-111">10 digits:</span></span>
  
-  <span data-ttu-id="42525-112">Drei Ziffern, die einer Seriennummer entsprechen</span><span class="sxs-lookup"><span data-stu-id="42525-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="42525-113">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="42525-113">One check digit</span></span>
    
- <span data-ttu-id="42525-114">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="42525-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42525-115">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="42525-115">Checksum</span></span>

<span data-ttu-id="42525-116">Ja</span><span class="sxs-lookup"><span data-stu-id="42525-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="42525-117">Definition</span><span class="sxs-lookup"><span data-stu-id="42525-117">Definition</span></span>

<span data-ttu-id="42525-118">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-119">Die- `Func_austria_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42525-120">Ein Schlüsselwort `Keywords_austria_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="42525-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="42525-121">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-122">Die- `Func_austria_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42525-123">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="42525-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="42525-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="42525-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="42525-125">Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-125">social security no</span></span>
  
<span data-ttu-id="42525-126">social security number</span><span class="sxs-lookup"><span data-stu-id="42525-126">social security number</span></span>
  
<span data-ttu-id="42525-127">social security code</span><span class="sxs-lookup"><span data-stu-id="42525-127">social security code</span></span>
  
<span data-ttu-id="42525-128">Versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-128">insurance number</span></span>
  
<span data-ttu-id="42525-129">Österreichische SSN</span><span class="sxs-lookup"><span data-stu-id="42525-129">austrian ssn</span></span>
  
<span data-ttu-id="42525-130">SSN #</span><span class="sxs-lookup"><span data-stu-id="42525-130">ssn#</span></span>
  
<span data-ttu-id="42525-131">SSN</span><span class="sxs-lookup"><span data-stu-id="42525-131">ssn</span></span>
  
<span data-ttu-id="42525-132">versicherungscode</span><span class="sxs-lookup"><span data-stu-id="42525-132">insurance code</span></span>
  
<span data-ttu-id="42525-133">versicherungscode #</span><span class="sxs-lookup"><span data-stu-id="42525-133">insurance code#</span></span>
  
<span data-ttu-id="42525-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="42525-134">socialsecurityno#</span></span>
  
<span data-ttu-id="42525-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="42525-136">soziale Sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="42525-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="42525-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="42525-138">Belgien</span><span class="sxs-lookup"><span data-stu-id="42525-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="42525-139">Format</span><span class="sxs-lookup"><span data-stu-id="42525-139">Format</span></span>

<span data-ttu-id="42525-140">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="42525-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42525-141">Muster</span><span class="sxs-lookup"><span data-stu-id="42525-141">Pattern</span></span>

<span data-ttu-id="42525-142">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="42525-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="42525-143">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="42525-143">Checksum</span></span>

<span data-ttu-id="42525-144">Ja</span><span class="sxs-lookup"><span data-stu-id="42525-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="42525-145">Definition</span><span class="sxs-lookup"><span data-stu-id="42525-145">Definition</span></span>

<span data-ttu-id="42525-146">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-147">Die- `Func_belgium_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42525-148">Ein Schlüsselwort `Keywords_belgium_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="42525-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="42525-149">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-150">Die- `Func_belgium_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42525-151">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="42525-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="42525-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="42525-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="42525-153">belgische nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-153">belgian national number</span></span>
  
<span data-ttu-id="42525-154">nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-154">national number</span></span>
  
<span data-ttu-id="42525-155">social security number</span><span class="sxs-lookup"><span data-stu-id="42525-155">social security number</span></span>
  
<span data-ttu-id="42525-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="42525-156">nationalnumber#</span></span>
  
<span data-ttu-id="42525-157">SSN #</span><span class="sxs-lookup"><span data-stu-id="42525-157">ssn#</span></span>
  
<span data-ttu-id="42525-158">SSN</span><span class="sxs-lookup"><span data-stu-id="42525-158">ssn</span></span>
  
<span data-ttu-id="42525-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="42525-159">nationalnumber</span></span>
  
<span data-ttu-id="42525-160">BNN #</span><span class="sxs-lookup"><span data-stu-id="42525-160">bnn#</span></span>
  
<span data-ttu-id="42525-161">BNN</span><span class="sxs-lookup"><span data-stu-id="42525-161">bnn</span></span>
  
<span data-ttu-id="42525-162">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-162">personal id number</span></span>
  
<span data-ttu-id="42525-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="42525-163">personalidnumber#</span></span>
  
<span data-ttu-id="42525-164">Numéro National</span><span class="sxs-lookup"><span data-stu-id="42525-164">numéro national</span></span>
  
<span data-ttu-id="42525-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="42525-165">numéro de sécurité</span></span>
  
<span data-ttu-id="42525-166">Numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="42525-166">numéro d'assuré</span></span>
  
<span data-ttu-id="42525-167">identifizierbare nationale</span><span class="sxs-lookup"><span data-stu-id="42525-167">identifiant national</span></span>
  
<span data-ttu-id="42525-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="42525-168">identifiantnational#</span></span>
  
<span data-ttu-id="42525-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="42525-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="42525-170">Kroatien</span><span class="sxs-lookup"><span data-stu-id="42525-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="42525-171">Format</span><span class="sxs-lookup"><span data-stu-id="42525-171">Format</span></span>

<span data-ttu-id="42525-172">11 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="42525-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42525-173">Muster</span><span class="sxs-lookup"><span data-stu-id="42525-173">Pattern</span></span>

 <span data-ttu-id="42525-174">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="42525-174">11 digits:</span></span> 
  
-  <span data-ttu-id="42525-175">Zehn Ziffern</span><span class="sxs-lookup"><span data-stu-id="42525-175">Ten digits</span></span> 
    
- <span data-ttu-id="42525-176">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="42525-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42525-177">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="42525-177">Checksum</span></span>

<span data-ttu-id="42525-178">Ja</span><span class="sxs-lookup"><span data-stu-id="42525-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="42525-179">Definition</span><span class="sxs-lookup"><span data-stu-id="42525-179">Definition</span></span>

<span data-ttu-id="42525-180">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-181">Die- `Func_croatia_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42525-182">Ein Schlüsselwort `Keywords_croatia_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="42525-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="42525-183">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-184">Die- `Func_croatia_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42525-185">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="42525-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="42525-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="42525-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="42525-187">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-187">personal identification number</span></span>
  
<span data-ttu-id="42525-188">Bürgermeister Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-188">master citizen number</span></span>
  
<span data-ttu-id="42525-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="42525-189">national identification number</span></span>
  
<span data-ttu-id="42525-190">social security number</span><span class="sxs-lookup"><span data-stu-id="42525-190">social security number</span></span>
  
<span data-ttu-id="42525-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="42525-191">nationalnumber#</span></span>
  
<span data-ttu-id="42525-192">SSN #</span><span class="sxs-lookup"><span data-stu-id="42525-192">ssn#</span></span>
  
<span data-ttu-id="42525-193">SSN</span><span class="sxs-lookup"><span data-stu-id="42525-193">ssn</span></span>
  
<span data-ttu-id="42525-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="42525-194">nationalnumber</span></span>
  
<span data-ttu-id="42525-195">BNN #</span><span class="sxs-lookup"><span data-stu-id="42525-195">bnn#</span></span>
  
<span data-ttu-id="42525-196">BNN</span><span class="sxs-lookup"><span data-stu-id="42525-196">bnn</span></span>
  
<span data-ttu-id="42525-197">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-197">personal id number</span></span>
  
<span data-ttu-id="42525-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="42525-198">personalidnumber#</span></span>
  
<span data-ttu-id="42525-199">OIB</span><span class="sxs-lookup"><span data-stu-id="42525-199">oib</span></span>
  
<span data-ttu-id="42525-200">Osobni identifikacijski Broj</span><span class="sxs-lookup"><span data-stu-id="42525-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="42525-201">Tschechien</span><span class="sxs-lookup"><span data-stu-id="42525-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="42525-202">Format</span><span class="sxs-lookup"><span data-stu-id="42525-202">Format</span></span>

<span data-ttu-id="42525-203">Zehn Ziffern und ein Backslash im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="42525-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42525-204">Muster</span><span class="sxs-lookup"><span data-stu-id="42525-204">Pattern</span></span>

<span data-ttu-id="42525-205">Zehn Ziffern und ein Backslash:</span><span class="sxs-lookup"><span data-stu-id="42525-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="42525-206">Sechs Ziffern, die dem Geburtsdatum (JJMMTT) entsprechen:</span><span class="sxs-lookup"><span data-stu-id="42525-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="42525-207">Einen umgekehrten Schrägstrich</span><span class="sxs-lookup"><span data-stu-id="42525-207">A backslash</span></span>
    
- <span data-ttu-id="42525-208">Drei Ziffern, die einer Seriennummer entsprechen, die Personen trennt, die am selben Datum geboren wurden</span><span class="sxs-lookup"><span data-stu-id="42525-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="42525-209">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="42525-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42525-210">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="42525-210">Checksum</span></span>

<span data-ttu-id="42525-211">Ja</span><span class="sxs-lookup"><span data-stu-id="42525-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="42525-212">Definition</span><span class="sxs-lookup"><span data-stu-id="42525-212">Definition</span></span>

<span data-ttu-id="42525-213">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-214">Die- `Func_czech_republic_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42525-215">Ein Schlüsselwort `Keywords_czech_republic_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="42525-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="42525-216">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-217">Die- `Func_czech_republic_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42525-218">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="42525-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="42525-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="42525-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="42525-220">Geburtsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-220">birth number</span></span>
  
<span data-ttu-id="42525-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="42525-221">national identification number</span></span>
  
<span data-ttu-id="42525-222">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-222">personal identification number</span></span>
  
<span data-ttu-id="42525-223">social security number</span><span class="sxs-lookup"><span data-stu-id="42525-223">social security number</span></span>
  
<span data-ttu-id="42525-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="42525-224">nationalnumber#</span></span>
  
<span data-ttu-id="42525-225">SSN #</span><span class="sxs-lookup"><span data-stu-id="42525-225">ssn#</span></span>
  
<span data-ttu-id="42525-226">SSN</span><span class="sxs-lookup"><span data-stu-id="42525-226">ssn</span></span>
  
<span data-ttu-id="42525-227">nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-227">national number</span></span>
  
<span data-ttu-id="42525-228">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-228">personal id number</span></span>
  
<span data-ttu-id="42525-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="42525-229">personalidnumber#</span></span>
  
<span data-ttu-id="42525-230">rč</span><span class="sxs-lookup"><span data-stu-id="42525-230">rč</span></span>
  
<span data-ttu-id="42525-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="42525-231">rodné číslo</span></span>
  
<span data-ttu-id="42525-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="42525-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="42525-233">Dänemark</span><span class="sxs-lookup"><span data-stu-id="42525-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="42525-234">Format</span><span class="sxs-lookup"><span data-stu-id="42525-234">Format</span></span>

<span data-ttu-id="42525-235">Zehn Ziffern und ein Bindestrich im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="42525-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42525-236">Muster</span><span class="sxs-lookup"><span data-stu-id="42525-236">Pattern</span></span>

<span data-ttu-id="42525-237">Zehn Ziffern und ein Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="42525-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="42525-238">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="42525-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="42525-239">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="42525-239">A hyphen</span></span>
    
- <span data-ttu-id="42525-240">Vier Ziffern, die einer Sequenznummer entsprechen</span><span class="sxs-lookup"><span data-stu-id="42525-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42525-241">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="42525-241">Checksum</span></span>

<span data-ttu-id="42525-242">Ja</span><span class="sxs-lookup"><span data-stu-id="42525-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="42525-243">Definition</span><span class="sxs-lookup"><span data-stu-id="42525-243">Definition</span></span>

<span data-ttu-id="42525-244">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-245">Die- `Func_denmark_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42525-246">Ein Schlüsselwort `Keywords_denmark_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="42525-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="42525-247">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-248">Die- `Func_denmark_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42525-249">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="42525-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="42525-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="42525-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="42525-251">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-251">personal identification number</span></span>
  
<span data-ttu-id="42525-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="42525-252">national identification number</span></span>
  
<span data-ttu-id="42525-253">social security number</span><span class="sxs-lookup"><span data-stu-id="42525-253">social security number</span></span>
  
<span data-ttu-id="42525-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="42525-254">nationalnumber#</span></span>
  
<span data-ttu-id="42525-255">SSN #</span><span class="sxs-lookup"><span data-stu-id="42525-255">ssn#</span></span>
  
<span data-ttu-id="42525-256">SSN</span><span class="sxs-lookup"><span data-stu-id="42525-256">ssn</span></span>
  
<span data-ttu-id="42525-257">nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-257">national number</span></span>
  
<span data-ttu-id="42525-258">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-258">personal id number</span></span>
  
<span data-ttu-id="42525-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="42525-259">personalidnumber#</span></span>
  
<span data-ttu-id="42525-260">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-260">cpr-nummer</span></span>
  
<span data-ttu-id="42525-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="42525-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="42525-262">Finnland</span><span class="sxs-lookup"><span data-stu-id="42525-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="42525-263">Format</span><span class="sxs-lookup"><span data-stu-id="42525-263">Format</span></span>

<span data-ttu-id="42525-264">Eine Kombination aus 11 Zeichen im angegebenen Format</span><span class="sxs-lookup"><span data-stu-id="42525-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42525-265">Muster</span><span class="sxs-lookup"><span data-stu-id="42525-265">Pattern</span></span>

<span data-ttu-id="42525-266">Eine Kombination aus 11 Zeichen im angegebenen Format:</span><span class="sxs-lookup"><span data-stu-id="42525-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="42525-267">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="42525-267">Six digits</span></span> 
    
- <span data-ttu-id="42525-268">Eine Instanz einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="42525-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="42525-269">Plus-Symbol</span><span class="sxs-lookup"><span data-stu-id="42525-269">Plus symbol</span></span>
    
  - <span data-ttu-id="42525-270">Minus Zeichen</span><span class="sxs-lookup"><span data-stu-id="42525-270">Minus symbol</span></span>
    
  - <span data-ttu-id="42525-271">Der Buchstabe "A" (Groß-/Kleinschreibung wird nicht berücksichtigt)</span><span class="sxs-lookup"><span data-stu-id="42525-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="42525-272">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="42525-272">Three digits</span></span>
    
- <span data-ttu-id="42525-273">Ein Buchstabe oder eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="42525-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42525-274">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="42525-274">Checksum</span></span>

<span data-ttu-id="42525-275">Ja</span><span class="sxs-lookup"><span data-stu-id="42525-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="42525-276">Definition</span><span class="sxs-lookup"><span data-stu-id="42525-276">Definition</span></span>

<span data-ttu-id="42525-277">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-278">Die- `Func_finland_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42525-279">Ein Schlüsselwort `Keywords_finland_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="42525-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="42525-280">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-281">Die- `Func_finland_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42525-282">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="42525-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="42525-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="42525-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="42525-284">identification number</span><span class="sxs-lookup"><span data-stu-id="42525-284">identification number</span></span>
  
<span data-ttu-id="42525-285">persönliche ID</span><span class="sxs-lookup"><span data-stu-id="42525-285">personal id</span></span>
  
<span data-ttu-id="42525-286">Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-286">identity number</span></span>
  
<span data-ttu-id="42525-287">Finnische Nationale ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-287">finnish national id number</span></span>
  
<span data-ttu-id="42525-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="42525-288">personalidnumber#</span></span>
  
<span data-ttu-id="42525-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="42525-289">national identification number</span></span>
  
<span data-ttu-id="42525-290">ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-290">id number</span></span>
  
<span data-ttu-id="42525-291">nationale ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="42525-291">national id no.</span></span>
  
<span data-ttu-id="42525-292">nationale ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-292">national id number</span></span>
  
<span data-ttu-id="42525-293">ID Nein</span><span class="sxs-lookup"><span data-stu-id="42525-293">id no</span></span>
  
<span data-ttu-id="42525-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="42525-294">tunnistenumero</span></span>
  
<span data-ttu-id="42525-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="42525-295">henkilötunnus</span></span>
  
<span data-ttu-id="42525-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="42525-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="42525-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="42525-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="42525-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="42525-298">identiteetti numero</span></span>
  
<span data-ttu-id="42525-299">Suomen der Kok henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="42525-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="42525-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="42525-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="42525-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="42525-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="42525-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="42525-302">tunnusnumero</span></span>
  
<span data-ttu-id="42525-303">der Kok tunnus numero</span><span class="sxs-lookup"><span data-stu-id="42525-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="42525-304">Hetu</span><span class="sxs-lookup"><span data-stu-id="42525-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="42525-305">Frankreich</span><span class="sxs-lookup"><span data-stu-id="42525-305">France</span></span>

<span data-ttu-id="42525-306">Ausführliche Informationen finden Sie im Abschnitt "französische Sozialversicherungsnummer (INSEE)" in [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="42525-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="42525-307">Deutschland</span><span class="sxs-lookup"><span data-stu-id="42525-307">Germany</span></span>

<span data-ttu-id="42525-308">Ausführliche Informationen finden Sie im Abschnitt "Deutsche Identitätskartennummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="42525-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="42525-309">Griechenland</span><span class="sxs-lookup"><span data-stu-id="42525-309">Greece</span></span>

<span data-ttu-id="42525-310">Ausführliche Informationen finden Sie im Abschnitt "Griechenland-National Ausweis" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="42525-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="42525-311">Ungarn</span><span class="sxs-lookup"><span data-stu-id="42525-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="42525-312">Format</span><span class="sxs-lookup"><span data-stu-id="42525-312">Format</span></span>

<span data-ttu-id="42525-313">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="42525-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42525-314">Muster</span><span class="sxs-lookup"><span data-stu-id="42525-314">Pattern</span></span>

<span data-ttu-id="42525-315">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="42525-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="42525-316">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="42525-316">Checksum</span></span>

<span data-ttu-id="42525-317">Ja</span><span class="sxs-lookup"><span data-stu-id="42525-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="42525-318">Definition</span><span class="sxs-lookup"><span data-stu-id="42525-318">Definition</span></span>

<span data-ttu-id="42525-319">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-320">Die- `Func_hungary_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42525-321">Ein Schlüsselwort `Keywords_hungary_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="42525-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="42525-322">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-323">Die- `Func_hungary_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42525-324">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="42525-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="42525-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="42525-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="42525-326">ungarische Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-326">hungarian social security number</span></span>
  
<span data-ttu-id="42525-327">social security number</span><span class="sxs-lookup"><span data-stu-id="42525-327">social security number</span></span>
  
<span data-ttu-id="42525-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="42525-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="42525-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="42525-329">hssn#</span></span>
  
<span data-ttu-id="42525-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="42525-330">socialsecuritynno</span></span>
  
<span data-ttu-id="42525-331">hssn</span><span class="sxs-lookup"><span data-stu-id="42525-331">hssn</span></span>
  
<span data-ttu-id="42525-332">Taj</span><span class="sxs-lookup"><span data-stu-id="42525-332">taj</span></span>
  
<span data-ttu-id="42525-333">Taj #</span><span class="sxs-lookup"><span data-stu-id="42525-333">taj#</span></span>
  
<span data-ttu-id="42525-334">SSN</span><span class="sxs-lookup"><span data-stu-id="42525-334">ssn</span></span>
  
<span data-ttu-id="42525-335">SSN #</span><span class="sxs-lookup"><span data-stu-id="42525-335">ssn#</span></span>
  
<span data-ttu-id="42525-336">Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-336">social security no</span></span>
  
<span data-ttu-id="42525-337">ÁFA</span><span class="sxs-lookup"><span data-stu-id="42525-337">áfa</span></span>
  
<span data-ttu-id="42525-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="42525-338">közösségi adószám</span></span>
  
<span data-ttu-id="42525-339">Általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="42525-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="42525-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="42525-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="42525-341">ÁFA szám</span><span class="sxs-lookup"><span data-stu-id="42525-341">áfa szám</span></span>
  
<span data-ttu-id="42525-342">Magyar ÁFA szám</span><span class="sxs-lookup"><span data-stu-id="42525-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="42525-343">Portugal</span><span class="sxs-lookup"><span data-stu-id="42525-343">Portugal</span></span>

<span data-ttu-id="42525-344">Ausführliche Informationen finden Sie im Abschnitt "Portugal-Bürgerkarten Nummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="42525-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="42525-345">Spanien</span><span class="sxs-lookup"><span data-stu-id="42525-345">Spain</span></span>

<span data-ttu-id="42525-346">Ausführliche Informationen finden Sie im Abschnitt "Spanien Sozialversicherungsnummer (SSN)" in [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="42525-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="42525-347">Schweden</span><span class="sxs-lookup"><span data-stu-id="42525-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="42525-348">Format</span><span class="sxs-lookup"><span data-stu-id="42525-348">Format</span></span>

<span data-ttu-id="42525-349">12 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="42525-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42525-350">Muster</span><span class="sxs-lookup"><span data-stu-id="42525-350">Pattern</span></span>

<span data-ttu-id="42525-351">12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="42525-351">12 digits:</span></span>
  
-  <span data-ttu-id="42525-352">Acht Ziffern, die dem Geburtsdatum entsprechen (JJJJMMTT)</span><span class="sxs-lookup"><span data-stu-id="42525-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="42525-353">Drei Ziffern, die einer Seriennummer entsprechen:</span><span class="sxs-lookup"><span data-stu-id="42525-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="42525-354">Die letzte Ziffer in der Seriennummer gibt das Geschlecht durch die Zuweisung einer ungeraden Zahl für männliche und eine gerade Zahl für weiblich an.</span><span class="sxs-lookup"><span data-stu-id="42525-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="42525-355">Bis zu 1990 entsprach die Zuordnung der Seriennummer dem Kreis, in dem der Inhaber der Nummer geboren wurde oder (sofern er vor 1947 geboren wurde), in dem er nach Steuerunterlagen am 1. Januar 1947 mit einem Sondercode (in der Regel 9 als siebte Ziffer) für Einwanderer gelebt hatte.</span><span class="sxs-lookup"><span data-stu-id="42525-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="42525-356">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="42525-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42525-357">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="42525-357">Checksum</span></span>

<span data-ttu-id="42525-358">Ja</span><span class="sxs-lookup"><span data-stu-id="42525-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="42525-359">Definition</span><span class="sxs-lookup"><span data-stu-id="42525-359">Definition</span></span>

<span data-ttu-id="42525-360">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-361">Die- `Func_sweden_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42525-362">Ein Schlüsselwort `Keywords_sweden_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="42525-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="42525-363">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42525-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42525-364">Die- `Func_sweden_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="42525-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42525-365">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="42525-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="42525-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="42525-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="42525-367">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-367">personal id number</span></span>
  
<span data-ttu-id="42525-368">identification number</span><span class="sxs-lookup"><span data-stu-id="42525-368">identification number</span></span>
  
<span data-ttu-id="42525-369">persönliche ID Nein</span><span class="sxs-lookup"><span data-stu-id="42525-369">personal id no</span></span>
  
<span data-ttu-id="42525-370">Identität Nein</span><span class="sxs-lookup"><span data-stu-id="42525-370">identity no</span></span>
  
<span data-ttu-id="42525-371">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-371">identification no</span></span>
  
<span data-ttu-id="42525-372">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="42525-372">personal identification no</span></span>
  
<span data-ttu-id="42525-373">PERSONNUMMER-ID</span><span class="sxs-lookup"><span data-stu-id="42525-373">personnummer id</span></span>
  
<span data-ttu-id="42525-374">personligt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-374">personligt id-nummer</span></span>
  
<span data-ttu-id="42525-375">unikt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="42525-375">unikt id-nummer</span></span>
  
<span data-ttu-id="42525-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="42525-376">personnummer</span></span>
  
<span data-ttu-id="42525-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="42525-377">identifikationsnumret</span></span>
  
<span data-ttu-id="42525-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="42525-378">personnummer#</span></span>
  
<span data-ttu-id="42525-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="42525-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="42525-380">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="42525-380">See also</span></span>

[<span data-ttu-id="42525-381">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="42525-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

