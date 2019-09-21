---
title: EU-Sozialversicherungsnummer oder gleichwertige ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn Sie die Sozialversicherungsnummer der EU oder einen entsprechenden ID-vertraulichen Informationstyp ermittelt. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: b42a8d927e18f813eb6ef6d1d55b2de15ea9dcd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081468"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="33f97-104">EU-Sozialversicherungsnummer oder gleichwertige ID</span><span class="sxs-lookup"><span data-stu-id="33f97-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="33f97-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn Sie den Typ der EU-Sozialversicherungsnummer (SSN) oder einen äquivalenten ID-vertraulichen Informationstyp erkennt.</span><span class="sxs-lookup"><span data-stu-id="33f97-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="33f97-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="33f97-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="33f97-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="33f97-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="33f97-108">Format</span><span class="sxs-lookup"><span data-stu-id="33f97-108">Format</span></span>

<span data-ttu-id="33f97-109">10 Ziffern im angegebenen Format</span><span class="sxs-lookup"><span data-stu-id="33f97-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f97-110">Muster</span><span class="sxs-lookup"><span data-stu-id="33f97-110">Pattern</span></span>

<span data-ttu-id="33f97-111">10 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="33f97-111">10 digits:</span></span>
  
-  <span data-ttu-id="33f97-112">Drei Ziffern, die einer Seriennummer entsprechen</span><span class="sxs-lookup"><span data-stu-id="33f97-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="33f97-113">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="33f97-113">One check digit</span></span>
    
- <span data-ttu-id="33f97-114">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="33f97-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f97-115">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33f97-115">Checksum</span></span>

<span data-ttu-id="33f97-116">Ja</span><span class="sxs-lookup"><span data-stu-id="33f97-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f97-117">Definition</span><span class="sxs-lookup"><span data-stu-id="33f97-117">Definition</span></span>

<span data-ttu-id="33f97-118">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-119">Die- `Func_austria_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f97-120">Ein Schlüsselwort `Keywords_austria_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33f97-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="33f97-121">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-122">Die- `Func_austria_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="33f97-123">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33f97-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="33f97-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="33f97-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="33f97-125">Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-125">social security no</span></span>
  
<span data-ttu-id="33f97-126">social security number</span><span class="sxs-lookup"><span data-stu-id="33f97-126">social security number</span></span>
  
<span data-ttu-id="33f97-127">social security code</span><span class="sxs-lookup"><span data-stu-id="33f97-127">social security code</span></span>
  
<span data-ttu-id="33f97-128">Versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-128">insurance number</span></span>
  
<span data-ttu-id="33f97-129">Österreichische SSN</span><span class="sxs-lookup"><span data-stu-id="33f97-129">austrian ssn</span></span>
  
<span data-ttu-id="33f97-130">SSN #</span><span class="sxs-lookup"><span data-stu-id="33f97-130">ssn#</span></span>
  
<span data-ttu-id="33f97-131">SSN</span><span class="sxs-lookup"><span data-stu-id="33f97-131">ssn</span></span>
  
<span data-ttu-id="33f97-132">versicherungscode</span><span class="sxs-lookup"><span data-stu-id="33f97-132">insurance code</span></span>
  
<span data-ttu-id="33f97-133">versicherungscode #</span><span class="sxs-lookup"><span data-stu-id="33f97-133">insurance code#</span></span>
  
<span data-ttu-id="33f97-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="33f97-134">socialsecurityno#</span></span>
  
<span data-ttu-id="33f97-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="33f97-136">soziale Sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="33f97-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="33f97-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="33f97-138">Belgien</span><span class="sxs-lookup"><span data-stu-id="33f97-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="33f97-139">Format</span><span class="sxs-lookup"><span data-stu-id="33f97-139">Format</span></span>

<span data-ttu-id="33f97-140">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33f97-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f97-141">Muster</span><span class="sxs-lookup"><span data-stu-id="33f97-141">Pattern</span></span>

<span data-ttu-id="33f97-142">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="33f97-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33f97-143">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33f97-143">Checksum</span></span>

<span data-ttu-id="33f97-144">Ja</span><span class="sxs-lookup"><span data-stu-id="33f97-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f97-145">Definition</span><span class="sxs-lookup"><span data-stu-id="33f97-145">Definition</span></span>

<span data-ttu-id="33f97-146">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-147">Die- `Func_belgium_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f97-148">Ein Schlüsselwort `Keywords_belgium_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33f97-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="33f97-149">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-150">Die- `Func_belgium_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="33f97-151">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33f97-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="33f97-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="33f97-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="33f97-153">belgische nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-153">belgian national number</span></span>
  
<span data-ttu-id="33f97-154">nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-154">national number</span></span>
  
<span data-ttu-id="33f97-155">social security number</span><span class="sxs-lookup"><span data-stu-id="33f97-155">social security number</span></span>
  
<span data-ttu-id="33f97-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="33f97-156">nationalnumber#</span></span>
  
<span data-ttu-id="33f97-157">SSN #</span><span class="sxs-lookup"><span data-stu-id="33f97-157">ssn#</span></span>
  
<span data-ttu-id="33f97-158">SSN</span><span class="sxs-lookup"><span data-stu-id="33f97-158">ssn</span></span>
  
<span data-ttu-id="33f97-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="33f97-159">nationalnumber</span></span>
  
<span data-ttu-id="33f97-160">BNN #</span><span class="sxs-lookup"><span data-stu-id="33f97-160">bnn#</span></span>
  
<span data-ttu-id="33f97-161">BNN</span><span class="sxs-lookup"><span data-stu-id="33f97-161">bnn</span></span>
  
<span data-ttu-id="33f97-162">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-162">personal id number</span></span>
  
<span data-ttu-id="33f97-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="33f97-163">personalidnumber#</span></span>
  
<span data-ttu-id="33f97-164">Numéro National</span><span class="sxs-lookup"><span data-stu-id="33f97-164">numéro national</span></span>
  
<span data-ttu-id="33f97-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="33f97-165">numéro de sécurité</span></span>
  
<span data-ttu-id="33f97-166">Numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="33f97-166">numéro d'assuré</span></span>
  
<span data-ttu-id="33f97-167">identifizierbare nationale</span><span class="sxs-lookup"><span data-stu-id="33f97-167">identifiant national</span></span>
  
<span data-ttu-id="33f97-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="33f97-168">identifiantnational#</span></span>
  
<span data-ttu-id="33f97-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="33f97-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="33f97-170">Kroatien</span><span class="sxs-lookup"><span data-stu-id="33f97-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="33f97-171">Format</span><span class="sxs-lookup"><span data-stu-id="33f97-171">Format</span></span>

<span data-ttu-id="33f97-172">11 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33f97-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f97-173">Muster</span><span class="sxs-lookup"><span data-stu-id="33f97-173">Pattern</span></span>

 <span data-ttu-id="33f97-174">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="33f97-174">11 digits:</span></span> 
  
-  <span data-ttu-id="33f97-175">Zehn Ziffern</span><span class="sxs-lookup"><span data-stu-id="33f97-175">Ten digits</span></span> 
    
- <span data-ttu-id="33f97-176">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="33f97-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f97-177">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33f97-177">Checksum</span></span>

<span data-ttu-id="33f97-178">Ja</span><span class="sxs-lookup"><span data-stu-id="33f97-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f97-179">Definition</span><span class="sxs-lookup"><span data-stu-id="33f97-179">Definition</span></span>

<span data-ttu-id="33f97-180">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-181">Die- `Func_croatia_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f97-182">Ein Schlüsselwort `Keywords_croatia_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33f97-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="33f97-183">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-184">Die- `Func_croatia_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="33f97-185">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33f97-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="33f97-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="33f97-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="33f97-187">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-187">personal identification number</span></span>
  
<span data-ttu-id="33f97-188">Bürgermeister Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-188">master citizen number</span></span>
  
<span data-ttu-id="33f97-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="33f97-189">national identification number</span></span>
  
<span data-ttu-id="33f97-190">social security number</span><span class="sxs-lookup"><span data-stu-id="33f97-190">social security number</span></span>
  
<span data-ttu-id="33f97-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="33f97-191">nationalnumber#</span></span>
  
<span data-ttu-id="33f97-192">SSN #</span><span class="sxs-lookup"><span data-stu-id="33f97-192">ssn#</span></span>
  
<span data-ttu-id="33f97-193">SSN</span><span class="sxs-lookup"><span data-stu-id="33f97-193">ssn</span></span>
  
<span data-ttu-id="33f97-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="33f97-194">nationalnumber</span></span>
  
<span data-ttu-id="33f97-195">BNN #</span><span class="sxs-lookup"><span data-stu-id="33f97-195">bnn#</span></span>
  
<span data-ttu-id="33f97-196">BNN</span><span class="sxs-lookup"><span data-stu-id="33f97-196">bnn</span></span>
  
<span data-ttu-id="33f97-197">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-197">personal id number</span></span>
  
<span data-ttu-id="33f97-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="33f97-198">personalidnumber#</span></span>
  
<span data-ttu-id="33f97-199">OIB</span><span class="sxs-lookup"><span data-stu-id="33f97-199">oib</span></span>
  
<span data-ttu-id="33f97-200">Osobni identifikacijski Broj</span><span class="sxs-lookup"><span data-stu-id="33f97-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="33f97-201">Tschechien</span><span class="sxs-lookup"><span data-stu-id="33f97-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="33f97-202">Format</span><span class="sxs-lookup"><span data-stu-id="33f97-202">Format</span></span>

<span data-ttu-id="33f97-203">Zehn Ziffern und ein Backslash im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="33f97-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f97-204">Muster</span><span class="sxs-lookup"><span data-stu-id="33f97-204">Pattern</span></span>

<span data-ttu-id="33f97-205">Zehn Ziffern und ein Backslash:</span><span class="sxs-lookup"><span data-stu-id="33f97-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="33f97-206">Sechs Ziffern, die dem Geburtsdatum (JJMMTT) entsprechen:</span><span class="sxs-lookup"><span data-stu-id="33f97-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="33f97-207">Einen umgekehrten Schrägstrich</span><span class="sxs-lookup"><span data-stu-id="33f97-207">A backslash</span></span>
    
- <span data-ttu-id="33f97-208">Drei Ziffern, die einer Seriennummer entsprechen, die Personen trennt, die am selben Datum geboren wurden</span><span class="sxs-lookup"><span data-stu-id="33f97-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="33f97-209">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="33f97-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f97-210">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33f97-210">Checksum</span></span>

<span data-ttu-id="33f97-211">Ja</span><span class="sxs-lookup"><span data-stu-id="33f97-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f97-212">Definition</span><span class="sxs-lookup"><span data-stu-id="33f97-212">Definition</span></span>

<span data-ttu-id="33f97-213">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-214">Die- `Func_czech_republic_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f97-215">Ein Schlüsselwort `Keywords_czech_republic_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33f97-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="33f97-216">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-217">Die- `Func_czech_republic_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="33f97-218">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33f97-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="33f97-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="33f97-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="33f97-220">Geburtsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-220">birth number</span></span>
  
<span data-ttu-id="33f97-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="33f97-221">national identification number</span></span>
  
<span data-ttu-id="33f97-222">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-222">personal identification number</span></span>
  
<span data-ttu-id="33f97-223">social security number</span><span class="sxs-lookup"><span data-stu-id="33f97-223">social security number</span></span>
  
<span data-ttu-id="33f97-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="33f97-224">nationalnumber#</span></span>
  
<span data-ttu-id="33f97-225">SSN #</span><span class="sxs-lookup"><span data-stu-id="33f97-225">ssn#</span></span>
  
<span data-ttu-id="33f97-226">SSN</span><span class="sxs-lookup"><span data-stu-id="33f97-226">ssn</span></span>
  
<span data-ttu-id="33f97-227">nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-227">national number</span></span>
  
<span data-ttu-id="33f97-228">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-228">personal id number</span></span>
  
<span data-ttu-id="33f97-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="33f97-229">personalidnumber#</span></span>
  
<span data-ttu-id="33f97-230">rč</span><span class="sxs-lookup"><span data-stu-id="33f97-230">rč</span></span>
  
<span data-ttu-id="33f97-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="33f97-231">rodné číslo</span></span>
  
<span data-ttu-id="33f97-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="33f97-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="33f97-233">Dänemark</span><span class="sxs-lookup"><span data-stu-id="33f97-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="33f97-234">Format</span><span class="sxs-lookup"><span data-stu-id="33f97-234">Format</span></span>

<span data-ttu-id="33f97-235">Zehn Ziffern und ein Bindestrich im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="33f97-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f97-236">Muster</span><span class="sxs-lookup"><span data-stu-id="33f97-236">Pattern</span></span>

<span data-ttu-id="33f97-237">Zehn Ziffern und ein Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="33f97-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="33f97-238">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="33f97-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="33f97-239">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="33f97-239">A hyphen</span></span>
    
- <span data-ttu-id="33f97-240">Vier Ziffern, die einer Sequenznummer entsprechen</span><span class="sxs-lookup"><span data-stu-id="33f97-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f97-241">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33f97-241">Checksum</span></span>

<span data-ttu-id="33f97-242">Ja</span><span class="sxs-lookup"><span data-stu-id="33f97-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f97-243">Definition</span><span class="sxs-lookup"><span data-stu-id="33f97-243">Definition</span></span>

<span data-ttu-id="33f97-244">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-245">Die- `Func_denmark_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f97-246">Ein Schlüsselwort `Keywords_denmark_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33f97-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="33f97-247">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-248">Die- `Func_denmark_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="33f97-249">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33f97-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="33f97-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="33f97-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="33f97-251">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-251">personal identification number</span></span>
  
<span data-ttu-id="33f97-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="33f97-252">national identification number</span></span>
  
<span data-ttu-id="33f97-253">social security number</span><span class="sxs-lookup"><span data-stu-id="33f97-253">social security number</span></span>
  
<span data-ttu-id="33f97-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="33f97-254">nationalnumber#</span></span>
  
<span data-ttu-id="33f97-255">SSN #</span><span class="sxs-lookup"><span data-stu-id="33f97-255">ssn#</span></span>
  
<span data-ttu-id="33f97-256">SSN</span><span class="sxs-lookup"><span data-stu-id="33f97-256">ssn</span></span>
  
<span data-ttu-id="33f97-257">nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-257">national number</span></span>
  
<span data-ttu-id="33f97-258">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-258">personal id number</span></span>
  
<span data-ttu-id="33f97-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="33f97-259">personalidnumber#</span></span>
  
<span data-ttu-id="33f97-260">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-260">cpr-nummer</span></span>
  
<span data-ttu-id="33f97-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="33f97-262">Finnland</span><span class="sxs-lookup"><span data-stu-id="33f97-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="33f97-263">Format</span><span class="sxs-lookup"><span data-stu-id="33f97-263">Format</span></span>

<span data-ttu-id="33f97-264">Eine Kombination aus 11 Zeichen im angegebenen Format</span><span class="sxs-lookup"><span data-stu-id="33f97-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f97-265">Muster</span><span class="sxs-lookup"><span data-stu-id="33f97-265">Pattern</span></span>

<span data-ttu-id="33f97-266">Eine Kombination aus 11 Zeichen im angegebenen Format:</span><span class="sxs-lookup"><span data-stu-id="33f97-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="33f97-267">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="33f97-267">Six digits</span></span> 
    
- <span data-ttu-id="33f97-268">Eine Instanz einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="33f97-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="33f97-269">Plus-Symbol</span><span class="sxs-lookup"><span data-stu-id="33f97-269">Plus symbol</span></span>
    
  - <span data-ttu-id="33f97-270">Minus Zeichen</span><span class="sxs-lookup"><span data-stu-id="33f97-270">Minus symbol</span></span>
    
  - <span data-ttu-id="33f97-271">Der Buchstabe "A" (Groß-/Kleinschreibung wird nicht berücksichtigt)</span><span class="sxs-lookup"><span data-stu-id="33f97-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="33f97-272">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="33f97-272">Three digits</span></span>
    
- <span data-ttu-id="33f97-273">Ein Buchstabe oder eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="33f97-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f97-274">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33f97-274">Checksum</span></span>

<span data-ttu-id="33f97-275">Ja</span><span class="sxs-lookup"><span data-stu-id="33f97-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f97-276">Definition</span><span class="sxs-lookup"><span data-stu-id="33f97-276">Definition</span></span>

<span data-ttu-id="33f97-277">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-278">Die- `Func_finland_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f97-279">Ein Schlüsselwort `Keywords_finland_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33f97-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="33f97-280">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-281">Die- `Func_finland_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="33f97-282">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33f97-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="33f97-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="33f97-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="33f97-284">identification number</span><span class="sxs-lookup"><span data-stu-id="33f97-284">identification number</span></span>
  
<span data-ttu-id="33f97-285">persönliche ID</span><span class="sxs-lookup"><span data-stu-id="33f97-285">personal id</span></span>
  
<span data-ttu-id="33f97-286">Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-286">identity number</span></span>
  
<span data-ttu-id="33f97-287">Finnische Nationale ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-287">finnish national id number</span></span>
  
<span data-ttu-id="33f97-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="33f97-288">personalidnumber#</span></span>
  
<span data-ttu-id="33f97-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="33f97-289">national identification number</span></span>
  
<span data-ttu-id="33f97-290">ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-290">id number</span></span>
  
<span data-ttu-id="33f97-291">nationale ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="33f97-291">national id no.</span></span>
  
<span data-ttu-id="33f97-292">nationale ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-292">national id number</span></span>
  
<span data-ttu-id="33f97-293">ID Nein</span><span class="sxs-lookup"><span data-stu-id="33f97-293">id no</span></span>
  
<span data-ttu-id="33f97-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="33f97-294">tunnistenumero</span></span>
  
<span data-ttu-id="33f97-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="33f97-295">henkilötunnus</span></span>
  
<span data-ttu-id="33f97-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="33f97-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="33f97-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="33f97-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="33f97-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="33f97-298">identiteetti numero</span></span>
  
<span data-ttu-id="33f97-299">Suomen der Kok henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="33f97-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="33f97-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="33f97-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="33f97-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="33f97-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="33f97-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="33f97-302">tunnusnumero</span></span>
  
<span data-ttu-id="33f97-303">der Kok tunnus numero</span><span class="sxs-lookup"><span data-stu-id="33f97-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="33f97-304">Hetu</span><span class="sxs-lookup"><span data-stu-id="33f97-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="33f97-305">Frankreich</span><span class="sxs-lookup"><span data-stu-id="33f97-305">France</span></span>

<span data-ttu-id="33f97-306">Ausführliche Informationen finden Sie im Abschnitt "französische Sozialversicherungsnummer (INSEE)" in [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="33f97-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="33f97-307">Deutschland</span><span class="sxs-lookup"><span data-stu-id="33f97-307">Germany</span></span>

<span data-ttu-id="33f97-308">Ausführliche Informationen finden Sie im Abschnitt "Deutsche Identitätskartennummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="33f97-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="33f97-309">Griechenland</span><span class="sxs-lookup"><span data-stu-id="33f97-309">Greece</span></span>

<span data-ttu-id="33f97-310">Ausführliche Informationen finden Sie im Abschnitt "Griechenland-National Ausweis" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="33f97-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="33f97-311">Ungarn</span><span class="sxs-lookup"><span data-stu-id="33f97-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="33f97-312">Format</span><span class="sxs-lookup"><span data-stu-id="33f97-312">Format</span></span>

<span data-ttu-id="33f97-313">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33f97-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f97-314">Muster</span><span class="sxs-lookup"><span data-stu-id="33f97-314">Pattern</span></span>

<span data-ttu-id="33f97-315">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="33f97-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33f97-316">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33f97-316">Checksum</span></span>

<span data-ttu-id="33f97-317">Ja</span><span class="sxs-lookup"><span data-stu-id="33f97-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f97-318">Definition</span><span class="sxs-lookup"><span data-stu-id="33f97-318">Definition</span></span>

<span data-ttu-id="33f97-319">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-320">Die- `Func_hungary_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f97-321">Ein Schlüsselwort `Keywords_hungary_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33f97-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="33f97-322">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-323">Die- `Func_hungary_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="33f97-324">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33f97-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="33f97-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="33f97-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="33f97-326">ungarische Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-326">hungarian social security number</span></span>
  
<span data-ttu-id="33f97-327">social security number</span><span class="sxs-lookup"><span data-stu-id="33f97-327">social security number</span></span>
  
<span data-ttu-id="33f97-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="33f97-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="33f97-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="33f97-329">hssn#</span></span>
  
<span data-ttu-id="33f97-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="33f97-330">socialsecuritynno</span></span>
  
<span data-ttu-id="33f97-331">hssn</span><span class="sxs-lookup"><span data-stu-id="33f97-331">hssn</span></span>
  
<span data-ttu-id="33f97-332">Taj</span><span class="sxs-lookup"><span data-stu-id="33f97-332">taj</span></span>
  
<span data-ttu-id="33f97-333">Taj #</span><span class="sxs-lookup"><span data-stu-id="33f97-333">taj#</span></span>
  
<span data-ttu-id="33f97-334">SSN</span><span class="sxs-lookup"><span data-stu-id="33f97-334">ssn</span></span>
  
<span data-ttu-id="33f97-335">SSN #</span><span class="sxs-lookup"><span data-stu-id="33f97-335">ssn#</span></span>
  
<span data-ttu-id="33f97-336">Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-336">social security no</span></span>
  
<span data-ttu-id="33f97-337">ÁFA</span><span class="sxs-lookup"><span data-stu-id="33f97-337">áfa</span></span>
  
<span data-ttu-id="33f97-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="33f97-338">közösségi adószám</span></span>
  
<span data-ttu-id="33f97-339">Általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="33f97-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="33f97-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="33f97-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="33f97-341">ÁFA szám</span><span class="sxs-lookup"><span data-stu-id="33f97-341">áfa szám</span></span>
  
<span data-ttu-id="33f97-342">Magyar ÁFA szám</span><span class="sxs-lookup"><span data-stu-id="33f97-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="33f97-343">Portugal</span><span class="sxs-lookup"><span data-stu-id="33f97-343">Portugal</span></span>

<span data-ttu-id="33f97-344">Ausführliche Informationen finden Sie im Abschnitt "Portugal-Bürgerkarten Nummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="33f97-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="33f97-345">Spanien</span><span class="sxs-lookup"><span data-stu-id="33f97-345">Spain</span></span>

<span data-ttu-id="33f97-346">Ausführliche Informationen finden Sie im Abschnitt "Spanien Sozialversicherungsnummer (SSN)" in [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="33f97-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="33f97-347">Schweden</span><span class="sxs-lookup"><span data-stu-id="33f97-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="33f97-348">Format</span><span class="sxs-lookup"><span data-stu-id="33f97-348">Format</span></span>

<span data-ttu-id="33f97-349">12 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33f97-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f97-350">Muster</span><span class="sxs-lookup"><span data-stu-id="33f97-350">Pattern</span></span>

<span data-ttu-id="33f97-351">12 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="33f97-351">12 digits:</span></span>
  
-  <span data-ttu-id="33f97-352">Acht Ziffern, die dem Geburtsdatum entsprechen (JJJJMMTT)</span><span class="sxs-lookup"><span data-stu-id="33f97-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="33f97-353">Drei Ziffern, die einer Seriennummer entsprechen:</span><span class="sxs-lookup"><span data-stu-id="33f97-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="33f97-354">Die letzte Ziffer in der Seriennummer gibt das Geschlecht durch die Zuweisung einer ungeraden Zahl für männliche und eine gerade Zahl für weiblich an.</span><span class="sxs-lookup"><span data-stu-id="33f97-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="33f97-355">Die Zuordnung der Seriennummer bis 1990 entsprach dem Kreis, in dem der Inhaber der Nummer geboren wurde oder (Falls vor 1947 geboren wurde), wo er nach Steuerprotokollen am 1. Januar 1947 mit einem Sondercode (in der Regel 9 als siebte Ziffer) lebte, für Einwanderer</span><span class="sxs-lookup"><span data-stu-id="33f97-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="33f97-356">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="33f97-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f97-357">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33f97-357">Checksum</span></span>

<span data-ttu-id="33f97-358">Ja</span><span class="sxs-lookup"><span data-stu-id="33f97-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f97-359">Definition</span><span class="sxs-lookup"><span data-stu-id="33f97-359">Definition</span></span>

<span data-ttu-id="33f97-360">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-361">Die- `Func_sweden_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f97-362">Ein Schlüsselwort `Keywords_sweden_eu_ssn_or_equivalent` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33f97-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="33f97-363">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33f97-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f97-364">Die- `Func_sweden_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33f97-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="33f97-365">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33f97-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="33f97-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="33f97-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="33f97-367">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-367">personal id number</span></span>
  
<span data-ttu-id="33f97-368">identification number</span><span class="sxs-lookup"><span data-stu-id="33f97-368">identification number</span></span>
  
<span data-ttu-id="33f97-369">persönliche ID Nein</span><span class="sxs-lookup"><span data-stu-id="33f97-369">personal id no</span></span>
  
<span data-ttu-id="33f97-370">Identität Nein</span><span class="sxs-lookup"><span data-stu-id="33f97-370">identity no</span></span>
  
<span data-ttu-id="33f97-371">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-371">identification no</span></span>
  
<span data-ttu-id="33f97-372">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-372">personal identification no</span></span>
  
<span data-ttu-id="33f97-373">PERSONNUMMER-ID</span><span class="sxs-lookup"><span data-stu-id="33f97-373">personnummer id</span></span>
  
<span data-ttu-id="33f97-374">personligt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-374">personligt id-nummer</span></span>
  
<span data-ttu-id="33f97-375">unikt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="33f97-375">unikt id-nummer</span></span>
  
<span data-ttu-id="33f97-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="33f97-376">personnummer</span></span>
  
<span data-ttu-id="33f97-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="33f97-377">identifikationsnumret</span></span>
  
<span data-ttu-id="33f97-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="33f97-378">personnummer#</span></span>
  
<span data-ttu-id="33f97-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="33f97-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="33f97-380">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33f97-380">See also</span></span>

[<span data-ttu-id="33f97-381">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="33f97-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

