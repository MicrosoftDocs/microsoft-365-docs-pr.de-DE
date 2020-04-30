---
title: EU-Sozialversicherungsnummer oder gleichwertige ID
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn Sie die Sozialversicherungsnummer der EU oder einen entsprechenden ID-vertraulichen Informationstyp ermittelt. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: 276b9f2d20c2c682df2a2072c1103ab9fc67a098
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938693"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="6315f-104">EU-Sozialversicherungsnummer oder gleichwertige ID</span><span class="sxs-lookup"><span data-stu-id="6315f-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="6315f-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn Sie den Typ der EU-Sozialversicherungsnummer (SSN) oder einen äquivalenten ID-vertraulichen Informationstyp erkennt.</span><span class="sxs-lookup"><span data-stu-id="6315f-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="6315f-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="6315f-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="6315f-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="6315f-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="6315f-108">Format</span><span class="sxs-lookup"><span data-stu-id="6315f-108">Format</span></span>

<span data-ttu-id="6315f-109">10 Ziffern im angegebenen Format</span><span class="sxs-lookup"><span data-stu-id="6315f-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6315f-110">Muster</span><span class="sxs-lookup"><span data-stu-id="6315f-110">Pattern</span></span>

<span data-ttu-id="6315f-111">10 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="6315f-111">10 digits:</span></span>
  
-  <span data-ttu-id="6315f-112">Drei Ziffern, die einer Seriennummer entsprechen</span><span class="sxs-lookup"><span data-stu-id="6315f-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="6315f-113">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="6315f-113">One check digit</span></span>
    
- <span data-ttu-id="6315f-114">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="6315f-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6315f-115">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="6315f-115">Checksum</span></span>

<span data-ttu-id="6315f-116">Ja</span><span class="sxs-lookup"><span data-stu-id="6315f-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6315f-117">Definition</span><span class="sxs-lookup"><span data-stu-id="6315f-117">Definition</span></span>

<span data-ttu-id="6315f-118">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-119">Die- `Func_austria_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6315f-120">Ein Schlüsselwort `Keywords_austria_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="6315f-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6315f-121">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-122">Die- `Func_austria_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6315f-123">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6315f-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="6315f-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6315f-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6315f-125">Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-125">social security no</span></span>
  
<span data-ttu-id="6315f-126">social security number</span><span class="sxs-lookup"><span data-stu-id="6315f-126">social security number</span></span>
  
<span data-ttu-id="6315f-127">social security code</span><span class="sxs-lookup"><span data-stu-id="6315f-127">social security code</span></span>
  
<span data-ttu-id="6315f-128">Versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-128">insurance number</span></span>
  
<span data-ttu-id="6315f-129">Österreichische SSN</span><span class="sxs-lookup"><span data-stu-id="6315f-129">austrian ssn</span></span>
  
<span data-ttu-id="6315f-130">SSN #</span><span class="sxs-lookup"><span data-stu-id="6315f-130">ssn#</span></span>
  
<span data-ttu-id="6315f-131">SSN</span><span class="sxs-lookup"><span data-stu-id="6315f-131">ssn</span></span>
  
<span data-ttu-id="6315f-132">versicherungscode</span><span class="sxs-lookup"><span data-stu-id="6315f-132">insurance code</span></span>
  
<span data-ttu-id="6315f-133">versicherungscode #</span><span class="sxs-lookup"><span data-stu-id="6315f-133">insurance code#</span></span>
  
<span data-ttu-id="6315f-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="6315f-134">socialsecurityno#</span></span>
  
<span data-ttu-id="6315f-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="6315f-136">soziale Sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="6315f-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="6315f-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="6315f-138">Belgien</span><span class="sxs-lookup"><span data-stu-id="6315f-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="6315f-139">Format</span><span class="sxs-lookup"><span data-stu-id="6315f-139">Format</span></span>

<span data-ttu-id="6315f-140">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="6315f-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6315f-141">Muster</span><span class="sxs-lookup"><span data-stu-id="6315f-141">Pattern</span></span>

<span data-ttu-id="6315f-142">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="6315f-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6315f-143">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="6315f-143">Checksum</span></span>

<span data-ttu-id="6315f-144">Ja</span><span class="sxs-lookup"><span data-stu-id="6315f-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6315f-145">Definition</span><span class="sxs-lookup"><span data-stu-id="6315f-145">Definition</span></span>

<span data-ttu-id="6315f-146">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-147">Die- `Func_belgium_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6315f-148">Ein Schlüsselwort `Keywords_belgium_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="6315f-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6315f-149">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-150">Die- `Func_belgium_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6315f-151">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6315f-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="6315f-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6315f-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6315f-153">belgische nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-153">belgian national number</span></span>
  
<span data-ttu-id="6315f-154">nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-154">national number</span></span>
  
<span data-ttu-id="6315f-155">social security number</span><span class="sxs-lookup"><span data-stu-id="6315f-155">social security number</span></span>
  
<span data-ttu-id="6315f-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="6315f-156">nationalnumber#</span></span>
  
<span data-ttu-id="6315f-157">SSN #</span><span class="sxs-lookup"><span data-stu-id="6315f-157">ssn#</span></span>
  
<span data-ttu-id="6315f-158">SSN</span><span class="sxs-lookup"><span data-stu-id="6315f-158">ssn</span></span>
  
<span data-ttu-id="6315f-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="6315f-159">nationalnumber</span></span>
  
<span data-ttu-id="6315f-160">BNN #</span><span class="sxs-lookup"><span data-stu-id="6315f-160">bnn#</span></span>
  
<span data-ttu-id="6315f-161">BNN</span><span class="sxs-lookup"><span data-stu-id="6315f-161">bnn</span></span>
  
<span data-ttu-id="6315f-162">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-162">personal id number</span></span>
  
<span data-ttu-id="6315f-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="6315f-163">personalidnumber#</span></span>
  
<span data-ttu-id="6315f-164">Numéro National</span><span class="sxs-lookup"><span data-stu-id="6315f-164">numéro national</span></span>
  
<span data-ttu-id="6315f-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="6315f-165">numéro de sécurité</span></span>
  
<span data-ttu-id="6315f-166">Numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="6315f-166">numéro d'assuré</span></span>
  
<span data-ttu-id="6315f-167">identifizierbare nationale</span><span class="sxs-lookup"><span data-stu-id="6315f-167">identifiant national</span></span>
  
<span data-ttu-id="6315f-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="6315f-168">identifiantnational#</span></span>
  
<span data-ttu-id="6315f-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="6315f-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="6315f-170">Kroatien</span><span class="sxs-lookup"><span data-stu-id="6315f-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="6315f-171">Format</span><span class="sxs-lookup"><span data-stu-id="6315f-171">Format</span></span>

<span data-ttu-id="6315f-172">11 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="6315f-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6315f-173">Muster</span><span class="sxs-lookup"><span data-stu-id="6315f-173">Pattern</span></span>

 <span data-ttu-id="6315f-174">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="6315f-174">11 digits:</span></span> 
  
-  <span data-ttu-id="6315f-175">Zehn Ziffern</span><span class="sxs-lookup"><span data-stu-id="6315f-175">Ten digits</span></span> 
    
- <span data-ttu-id="6315f-176">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="6315f-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6315f-177">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="6315f-177">Checksum</span></span>

<span data-ttu-id="6315f-178">Ja</span><span class="sxs-lookup"><span data-stu-id="6315f-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6315f-179">Definition</span><span class="sxs-lookup"><span data-stu-id="6315f-179">Definition</span></span>

<span data-ttu-id="6315f-180">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-181">Die- `Func_croatia_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6315f-182">Ein Schlüsselwort `Keywords_croatia_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="6315f-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6315f-183">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-184">Die- `Func_croatia_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6315f-185">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6315f-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="6315f-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6315f-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6315f-187">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-187">personal identification number</span></span>
  
<span data-ttu-id="6315f-188">Bürgermeister Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-188">master citizen number</span></span>
  
<span data-ttu-id="6315f-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="6315f-189">national identification number</span></span>
  
<span data-ttu-id="6315f-190">social security number</span><span class="sxs-lookup"><span data-stu-id="6315f-190">social security number</span></span>
  
<span data-ttu-id="6315f-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="6315f-191">nationalnumber#</span></span>
  
<span data-ttu-id="6315f-192">SSN #</span><span class="sxs-lookup"><span data-stu-id="6315f-192">ssn#</span></span>
  
<span data-ttu-id="6315f-193">SSN</span><span class="sxs-lookup"><span data-stu-id="6315f-193">ssn</span></span>
  
<span data-ttu-id="6315f-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="6315f-194">nationalnumber</span></span>
  
<span data-ttu-id="6315f-195">BNN #</span><span class="sxs-lookup"><span data-stu-id="6315f-195">bnn#</span></span>
  
<span data-ttu-id="6315f-196">BNN</span><span class="sxs-lookup"><span data-stu-id="6315f-196">bnn</span></span>
  
<span data-ttu-id="6315f-197">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-197">personal id number</span></span>
  
<span data-ttu-id="6315f-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="6315f-198">personalidnumber#</span></span>
  
<span data-ttu-id="6315f-199">OIB</span><span class="sxs-lookup"><span data-stu-id="6315f-199">oib</span></span>
  
<span data-ttu-id="6315f-200">Osobni identifikacijski Broj</span><span class="sxs-lookup"><span data-stu-id="6315f-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="6315f-201">Tschechien</span><span class="sxs-lookup"><span data-stu-id="6315f-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="6315f-202">Format</span><span class="sxs-lookup"><span data-stu-id="6315f-202">Format</span></span>

<span data-ttu-id="6315f-203">Zehn Ziffern und ein Backslash im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="6315f-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6315f-204">Muster</span><span class="sxs-lookup"><span data-stu-id="6315f-204">Pattern</span></span>

<span data-ttu-id="6315f-205">Zehn Ziffern und ein Backslash:</span><span class="sxs-lookup"><span data-stu-id="6315f-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="6315f-206">Sechs Ziffern, die dem Geburtsdatum (JJMMTT) entsprechen:</span><span class="sxs-lookup"><span data-stu-id="6315f-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="6315f-207">Einen umgekehrten Schrägstrich</span><span class="sxs-lookup"><span data-stu-id="6315f-207">A backslash</span></span>
    
- <span data-ttu-id="6315f-208">Drei Ziffern, die einer Seriennummer entsprechen, die Personen trennt, die am selben Datum geboren wurden</span><span class="sxs-lookup"><span data-stu-id="6315f-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="6315f-209">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="6315f-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6315f-210">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="6315f-210">Checksum</span></span>

<span data-ttu-id="6315f-211">Ja</span><span class="sxs-lookup"><span data-stu-id="6315f-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6315f-212">Definition</span><span class="sxs-lookup"><span data-stu-id="6315f-212">Definition</span></span>

<span data-ttu-id="6315f-213">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-214">Die- `Func_czech_republic_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6315f-215">Ein Schlüsselwort `Keywords_czech_republic_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="6315f-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6315f-216">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-217">Die- `Func_czech_republic_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6315f-218">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6315f-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="6315f-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6315f-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6315f-220">Geburtsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-220">birth number</span></span>
  
<span data-ttu-id="6315f-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="6315f-221">national identification number</span></span>
  
<span data-ttu-id="6315f-222">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-222">personal identification number</span></span>
  
<span data-ttu-id="6315f-223">social security number</span><span class="sxs-lookup"><span data-stu-id="6315f-223">social security number</span></span>
  
<span data-ttu-id="6315f-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="6315f-224">nationalnumber#</span></span>
  
<span data-ttu-id="6315f-225">SSN #</span><span class="sxs-lookup"><span data-stu-id="6315f-225">ssn#</span></span>
  
<span data-ttu-id="6315f-226">SSN</span><span class="sxs-lookup"><span data-stu-id="6315f-226">ssn</span></span>
  
<span data-ttu-id="6315f-227">nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-227">national number</span></span>
  
<span data-ttu-id="6315f-228">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-228">personal id number</span></span>
  
<span data-ttu-id="6315f-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="6315f-229">personalidnumber#</span></span>
  
<span data-ttu-id="6315f-230">rč</span><span class="sxs-lookup"><span data-stu-id="6315f-230">rč</span></span>
  
<span data-ttu-id="6315f-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="6315f-231">rodné číslo</span></span>
  
<span data-ttu-id="6315f-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="6315f-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="6315f-233">Dänemark</span><span class="sxs-lookup"><span data-stu-id="6315f-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="6315f-234">Format</span><span class="sxs-lookup"><span data-stu-id="6315f-234">Format</span></span>

<span data-ttu-id="6315f-235">Zehn Ziffern und ein Bindestrich im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="6315f-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6315f-236">Muster</span><span class="sxs-lookup"><span data-stu-id="6315f-236">Pattern</span></span>

<span data-ttu-id="6315f-237">Zehn Ziffern und ein Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="6315f-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="6315f-238">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="6315f-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="6315f-239">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="6315f-239">A hyphen</span></span>
    
- <span data-ttu-id="6315f-240">Vier Ziffern, die einer Sequenznummer entsprechen</span><span class="sxs-lookup"><span data-stu-id="6315f-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6315f-241">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="6315f-241">Checksum</span></span>

<span data-ttu-id="6315f-242">Ja</span><span class="sxs-lookup"><span data-stu-id="6315f-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6315f-243">Definition</span><span class="sxs-lookup"><span data-stu-id="6315f-243">Definition</span></span>

<span data-ttu-id="6315f-244">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-245">Die- `Func_denmark_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6315f-246">Ein Schlüsselwort `Keywords_denmark_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="6315f-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6315f-247">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-248">Die- `Func_denmark_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6315f-249">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6315f-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="6315f-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6315f-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6315f-251">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-251">personal identification number</span></span>
  
<span data-ttu-id="6315f-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="6315f-252">national identification number</span></span>
  
<span data-ttu-id="6315f-253">social security number</span><span class="sxs-lookup"><span data-stu-id="6315f-253">social security number</span></span>
  
<span data-ttu-id="6315f-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="6315f-254">nationalnumber#</span></span>
  
<span data-ttu-id="6315f-255">SSN #</span><span class="sxs-lookup"><span data-stu-id="6315f-255">ssn#</span></span>
  
<span data-ttu-id="6315f-256">SSN</span><span class="sxs-lookup"><span data-stu-id="6315f-256">ssn</span></span>
  
<span data-ttu-id="6315f-257">nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-257">national number</span></span>
  
<span data-ttu-id="6315f-258">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-258">personal id number</span></span>
  
<span data-ttu-id="6315f-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="6315f-259">personalidnumber#</span></span>
  
<span data-ttu-id="6315f-260">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-260">cpr-nummer</span></span>
  
<span data-ttu-id="6315f-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="6315f-262">Finnland</span><span class="sxs-lookup"><span data-stu-id="6315f-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="6315f-263">Format</span><span class="sxs-lookup"><span data-stu-id="6315f-263">Format</span></span>

<span data-ttu-id="6315f-264">Eine Kombination aus 11 Zeichen im angegebenen Format</span><span class="sxs-lookup"><span data-stu-id="6315f-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6315f-265">Muster</span><span class="sxs-lookup"><span data-stu-id="6315f-265">Pattern</span></span>

<span data-ttu-id="6315f-266">Eine Kombination aus 11 Zeichen im angegebenen Format:</span><span class="sxs-lookup"><span data-stu-id="6315f-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="6315f-267">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="6315f-267">Six digits</span></span> 
    
- <span data-ttu-id="6315f-268">Eine Instanz einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="6315f-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="6315f-269">Plus-Symbol</span><span class="sxs-lookup"><span data-stu-id="6315f-269">Plus symbol</span></span>
    
  - <span data-ttu-id="6315f-270">Minus Zeichen</span><span class="sxs-lookup"><span data-stu-id="6315f-270">Minus symbol</span></span>
    
  - <span data-ttu-id="6315f-271">Der Buchstabe "A" (Groß-/Kleinschreibung wird nicht berücksichtigt)</span><span class="sxs-lookup"><span data-stu-id="6315f-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="6315f-272">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="6315f-272">Three digits</span></span>
    
- <span data-ttu-id="6315f-273">Ein Buchstabe oder eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="6315f-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6315f-274">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="6315f-274">Checksum</span></span>

<span data-ttu-id="6315f-275">Ja</span><span class="sxs-lookup"><span data-stu-id="6315f-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6315f-276">Definition</span><span class="sxs-lookup"><span data-stu-id="6315f-276">Definition</span></span>

<span data-ttu-id="6315f-277">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-278">Die- `Func_finland_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6315f-279">Ein Schlüsselwort `Keywords_finland_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="6315f-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6315f-280">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-281">Die- `Func_finland_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6315f-282">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6315f-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="6315f-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6315f-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6315f-284">identification number</span><span class="sxs-lookup"><span data-stu-id="6315f-284">identification number</span></span>
  
<span data-ttu-id="6315f-285">persönliche ID</span><span class="sxs-lookup"><span data-stu-id="6315f-285">personal id</span></span>
  
<span data-ttu-id="6315f-286">Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-286">identity number</span></span>
  
<span data-ttu-id="6315f-287">Finnische Nationale ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-287">finnish national id number</span></span>
  
<span data-ttu-id="6315f-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="6315f-288">personalidnumber#</span></span>
  
<span data-ttu-id="6315f-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="6315f-289">national identification number</span></span>
  
<span data-ttu-id="6315f-290">ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-290">id number</span></span>
  
<span data-ttu-id="6315f-291">nationale ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="6315f-291">national id no.</span></span>
  
<span data-ttu-id="6315f-292">nationale ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-292">national id number</span></span>
  
<span data-ttu-id="6315f-293">ID Nein</span><span class="sxs-lookup"><span data-stu-id="6315f-293">id no</span></span>
  
<span data-ttu-id="6315f-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="6315f-294">tunnistenumero</span></span>
  
<span data-ttu-id="6315f-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="6315f-295">henkilötunnus</span></span>
  
<span data-ttu-id="6315f-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="6315f-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="6315f-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="6315f-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="6315f-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="6315f-298">identiteetti numero</span></span>
  
<span data-ttu-id="6315f-299">Suomen der Kok henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="6315f-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="6315f-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="6315f-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="6315f-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="6315f-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="6315f-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="6315f-302">tunnusnumero</span></span>
  
<span data-ttu-id="6315f-303">der Kok tunnus numero</span><span class="sxs-lookup"><span data-stu-id="6315f-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="6315f-304">Hetu</span><span class="sxs-lookup"><span data-stu-id="6315f-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="6315f-305">Frankreich</span><span class="sxs-lookup"><span data-stu-id="6315f-305">France</span></span>

<span data-ttu-id="6315f-306">Ausführliche Informationen finden Sie im Abschnitt "französische Sozialversicherungsnummer (INSEE)" in [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6315f-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="6315f-307">Deutschland</span><span class="sxs-lookup"><span data-stu-id="6315f-307">Germany</span></span>

<span data-ttu-id="6315f-308">Ausführliche Informationen finden Sie im Abschnitt "Deutsche Identitätskartennummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6315f-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="6315f-309">Griechenland</span><span class="sxs-lookup"><span data-stu-id="6315f-309">Greece</span></span>

<span data-ttu-id="6315f-310">Ausführliche Informationen finden Sie im Abschnitt "Griechenland-National Ausweis" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6315f-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="6315f-311">Ungarn</span><span class="sxs-lookup"><span data-stu-id="6315f-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="6315f-312">Format</span><span class="sxs-lookup"><span data-stu-id="6315f-312">Format</span></span>

<span data-ttu-id="6315f-313">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="6315f-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6315f-314">Muster</span><span class="sxs-lookup"><span data-stu-id="6315f-314">Pattern</span></span>

<span data-ttu-id="6315f-315">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="6315f-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6315f-316">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="6315f-316">Checksum</span></span>

<span data-ttu-id="6315f-317">Ja</span><span class="sxs-lookup"><span data-stu-id="6315f-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6315f-318">Definition</span><span class="sxs-lookup"><span data-stu-id="6315f-318">Definition</span></span>

<span data-ttu-id="6315f-319">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-320">Die- `Func_hungary_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6315f-321">Ein Schlüsselwort `Keywords_hungary_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="6315f-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6315f-322">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-323">Die- `Func_hungary_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6315f-324">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6315f-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="6315f-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6315f-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6315f-326">ungarische Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-326">hungarian social security number</span></span>
  
<span data-ttu-id="6315f-327">social security number</span><span class="sxs-lookup"><span data-stu-id="6315f-327">social security number</span></span>
  
<span data-ttu-id="6315f-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="6315f-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="6315f-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="6315f-329">hssn#</span></span>
  
<span data-ttu-id="6315f-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="6315f-330">socialsecuritynno</span></span>
  
<span data-ttu-id="6315f-331">hssn</span><span class="sxs-lookup"><span data-stu-id="6315f-331">hssn</span></span>
  
<span data-ttu-id="6315f-332">Taj</span><span class="sxs-lookup"><span data-stu-id="6315f-332">taj</span></span>
  
<span data-ttu-id="6315f-333">Taj #</span><span class="sxs-lookup"><span data-stu-id="6315f-333">taj#</span></span>
  
<span data-ttu-id="6315f-334">SSN</span><span class="sxs-lookup"><span data-stu-id="6315f-334">ssn</span></span>
  
<span data-ttu-id="6315f-335">SSN #</span><span class="sxs-lookup"><span data-stu-id="6315f-335">ssn#</span></span>
  
<span data-ttu-id="6315f-336">Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-336">social security no</span></span>
  
<span data-ttu-id="6315f-337">ÁFA</span><span class="sxs-lookup"><span data-stu-id="6315f-337">áfa</span></span>
  
<span data-ttu-id="6315f-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="6315f-338">közösségi adószám</span></span>
  
<span data-ttu-id="6315f-339">Általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="6315f-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="6315f-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="6315f-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="6315f-341">ÁFA szám</span><span class="sxs-lookup"><span data-stu-id="6315f-341">áfa szám</span></span>
  
<span data-ttu-id="6315f-342">Magyar ÁFA szám</span><span class="sxs-lookup"><span data-stu-id="6315f-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="6315f-343">Portugal</span><span class="sxs-lookup"><span data-stu-id="6315f-343">Portugal</span></span>

<span data-ttu-id="6315f-344">Ausführliche Informationen finden Sie im Abschnitt "Portugal-Bürgerkarten Nummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6315f-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="6315f-345">Spanien</span><span class="sxs-lookup"><span data-stu-id="6315f-345">Spain</span></span>

<span data-ttu-id="6315f-346">Ausführliche Informationen finden Sie im Abschnitt "Spanien Sozialversicherungsnummer (SSN)" in [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6315f-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="6315f-347">Schweden</span><span class="sxs-lookup"><span data-stu-id="6315f-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="6315f-348">Format</span><span class="sxs-lookup"><span data-stu-id="6315f-348">Format</span></span>

<span data-ttu-id="6315f-349">12 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="6315f-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6315f-350">Muster</span><span class="sxs-lookup"><span data-stu-id="6315f-350">Pattern</span></span>

<span data-ttu-id="6315f-351">12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="6315f-351">12 digits:</span></span>
  
-  <span data-ttu-id="6315f-352">Acht Ziffern, die dem Geburtsdatum entsprechen (JJJJMMTT)</span><span class="sxs-lookup"><span data-stu-id="6315f-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="6315f-353">Drei Ziffern, die einer Seriennummer entsprechen:</span><span class="sxs-lookup"><span data-stu-id="6315f-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="6315f-354">Die letzte Ziffer in der Seriennummer gibt das Geschlecht durch die Zuweisung einer ungeraden Zahl für männliche und eine gerade Zahl für weiblich an.</span><span class="sxs-lookup"><span data-stu-id="6315f-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="6315f-355">Bis zu 1990 entsprach die Zuordnung der Seriennummer dem Kreis, in dem der Inhaber der Nummer geboren wurde oder (sofern er vor 1947 geboren wurde), in dem er nach Steuerunterlagen am 1. Januar 1947 mit einem Sondercode (in der Regel 9 als siebte Ziffer) für Einwanderer gelebt hatte.</span><span class="sxs-lookup"><span data-stu-id="6315f-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="6315f-356">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="6315f-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6315f-357">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="6315f-357">Checksum</span></span>

<span data-ttu-id="6315f-358">Ja</span><span class="sxs-lookup"><span data-stu-id="6315f-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6315f-359">Definition</span><span class="sxs-lookup"><span data-stu-id="6315f-359">Definition</span></span>

<span data-ttu-id="6315f-360">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-361">Die- `Func_sweden_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6315f-362">Ein Schlüsselwort `Keywords_sweden_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="6315f-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6315f-363">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6315f-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6315f-364">Die- `Func_sweden_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6315f-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6315f-365">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6315f-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="6315f-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6315f-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6315f-367">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-367">personal id number</span></span>
  
<span data-ttu-id="6315f-368">identification number</span><span class="sxs-lookup"><span data-stu-id="6315f-368">identification number</span></span>
  
<span data-ttu-id="6315f-369">persönliche ID Nein</span><span class="sxs-lookup"><span data-stu-id="6315f-369">personal id no</span></span>
  
<span data-ttu-id="6315f-370">Identität Nein</span><span class="sxs-lookup"><span data-stu-id="6315f-370">identity no</span></span>
  
<span data-ttu-id="6315f-371">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-371">identification no</span></span>
  
<span data-ttu-id="6315f-372">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-372">personal identification no</span></span>
  
<span data-ttu-id="6315f-373">PERSONNUMMER-ID</span><span class="sxs-lookup"><span data-stu-id="6315f-373">personnummer id</span></span>
  
<span data-ttu-id="6315f-374">personligt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-374">personligt id-nummer</span></span>
  
<span data-ttu-id="6315f-375">unikt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="6315f-375">unikt id-nummer</span></span>
  
<span data-ttu-id="6315f-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="6315f-376">personnummer</span></span>
  
<span data-ttu-id="6315f-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="6315f-377">identifikationsnumret</span></span>
  
<span data-ttu-id="6315f-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="6315f-378">personnummer#</span></span>
  
<span data-ttu-id="6315f-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="6315f-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6315f-380">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6315f-380">See also</span></span>

[<span data-ttu-id="6315f-381">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="6315f-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

