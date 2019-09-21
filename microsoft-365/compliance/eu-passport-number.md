---
title: EU-Passport-Nummer
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp EU-Passport-Nummern erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081471"
---
# <a name="eu-passport-number"></a><span data-ttu-id="82d22-104">EU-Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-104">EU Passport Number</span></span>

<span data-ttu-id="82d22-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp EU-Passport-Nummern erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="82d22-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="82d22-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="82d22-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="82d22-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="82d22-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="82d22-108">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-108">Format</span></span>

<span data-ttu-id="82d22-109">Ein Buchstabe, gefolgt von einem optionalen Leerzeichen und sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-110">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-110">Pattern</span></span>

<span data-ttu-id="82d22-111">Eine Kombination aus einem Buchstaben, sieben Ziffern und einem Leerzeichen:</span><span class="sxs-lookup"><span data-stu-id="82d22-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="82d22-112">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="82d22-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="82d22-113">Ein Leerzeichen (optional)</span><span class="sxs-lookup"><span data-stu-id="82d22-113">One space (optional)</span></span>
    
- <span data-ttu-id="82d22-114">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="82d22-115">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-115">Checksum</span></span>

<span data-ttu-id="82d22-116">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="82d22-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-117">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-117">Definition</span></span>

<span data-ttu-id="82d22-118">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-119">Der reguläre Ausdruck `Regex_austria_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-120">Ein Schlüsselwort `Keywords_austria_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-121">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-121">Keywords</span></span>

<span data-ttu-id="82d22-122">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-122"></span></span>
|<span data-ttu-id="82d22-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-124">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-124">passport number</span></span>  <br/> <span data-ttu-id="82d22-125">Österreichische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-125">austrian passport number</span></span>  <br/> <span data-ttu-id="82d22-126">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-126">passport no</span></span>  <br/> <span data-ttu-id="82d22-127">Reisepass</span><span class="sxs-lookup"><span data-stu-id="82d22-127">reisepass</span></span>  <br/> <span data-ttu-id="82d22-128">österreichisch Reisepass</span><span class="sxs-lookup"><span data-stu-id="82d22-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="82d22-129">Belgien</span><span class="sxs-lookup"><span data-stu-id="82d22-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="82d22-130">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-130">Format</span></span>

<span data-ttu-id="82d22-131">Zwei Buchstaben, gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-132">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-132">Pattern</span></span>

<span data-ttu-id="82d22-133">Zwei Buchstaben und gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="82d22-134">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-134">Checksum</span></span>

<span data-ttu-id="82d22-135">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="82d22-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-136">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-136">Definition</span></span>

<span data-ttu-id="82d22-137">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-138">Der reguläre Ausdruck `Regex_belgium_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-139">Ein Schlüsselwort `Keywords_belgium_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-140">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-140">Keywords</span></span>

<span data-ttu-id="82d22-141">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-141"></span></span>
|<span data-ttu-id="82d22-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-143">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-143">passport number</span></span>  <br/> <span data-ttu-id="82d22-144">belgische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-144">belgian passport number</span></span>  <br/> <span data-ttu-id="82d22-145">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-145">passport no</span></span>  <br/> <span data-ttu-id="82d22-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="82d22-146">paspoort</span></span>  <br/> <span data-ttu-id="82d22-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="82d22-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="82d22-148">reisepass kein</span></span>  <br/> <span data-ttu-id="82d22-149">Reisepass</span><span class="sxs-lookup"><span data-stu-id="82d22-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="82d22-150">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="82d22-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="82d22-151">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-151">Format</span></span>

<span data-ttu-id="82d22-152">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-153">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-153">Pattern</span></span>

 <span data-ttu-id="82d22-154">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="82d22-155">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-155">Checksum</span></span>

<span data-ttu-id="82d22-156">No</span><span class="sxs-lookup"><span data-stu-id="82d22-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-157">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-157">Definition</span></span>

<span data-ttu-id="82d22-158">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-159">Der reguläre Ausdruck `Regex_bulgaria_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-160">Ein Schlüsselwort `Keywords_bulgaria_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-161">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-161">Keywords</span></span>

<span data-ttu-id="82d22-162">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-162"></span></span>
|<span data-ttu-id="82d22-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-164">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-164">passport number</span></span>  <br/> <span data-ttu-id="82d22-165">Bulgarische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="82d22-166">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-166">passport no</span></span>  <br/> <span data-ttu-id="82d22-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="82d22-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="82d22-168">Kroatien</span><span class="sxs-lookup"><span data-stu-id="82d22-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="82d22-169">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-169">Format</span></span>

<span data-ttu-id="82d22-170">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-171">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-171">Pattern</span></span>

 <span data-ttu-id="82d22-172">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="82d22-173">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-173">Checksum</span></span>

<span data-ttu-id="82d22-174">No</span><span class="sxs-lookup"><span data-stu-id="82d22-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-175">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-175">Definition</span></span>

<span data-ttu-id="82d22-176">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-177">Der reguläre Ausdruck `Regex_croatia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-178">Ein Schlüsselwort `Keywords_croatia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-179">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-179">Keywords</span></span>

<span data-ttu-id="82d22-180">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-180"></span></span>
|<span data-ttu-id="82d22-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-182">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-182">passport number</span></span>  <br/> <span data-ttu-id="82d22-183">Kroatische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-183">croatian passport number</span></span>  <br/> <span data-ttu-id="82d22-184">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-184">passport no</span></span>  <br/> <span data-ttu-id="82d22-185">Broj putovnice</span><span class="sxs-lookup"><span data-stu-id="82d22-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="82d22-186">Zypern</span><span class="sxs-lookup"><span data-stu-id="82d22-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="82d22-187">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-187">Format</span></span>

<span data-ttu-id="82d22-188">Ein Buchstabe, gefolgt von 6-8 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-189">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-189">Pattern</span></span>

<span data-ttu-id="82d22-190">Ein Buchstabe, gefolgt von sechs bis acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="82d22-191">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-191">Checksum</span></span>

<span data-ttu-id="82d22-192">No</span><span class="sxs-lookup"><span data-stu-id="82d22-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-193">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-193">Definition</span></span>

<span data-ttu-id="82d22-194">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-195">Der reguläre Ausdruck `Regex_cyprus_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-196">Ein Schlüsselwort `Keywords_cyprus_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-197">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-197">Keywords</span></span>

<span data-ttu-id="82d22-198">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-198"></span></span>
|<span data-ttu-id="82d22-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-200">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-200">passport number</span></span>  <br/> <span data-ttu-id="82d22-201">Zypern-Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="82d22-202">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-202">passport no</span></span>  <br/> <span data-ttu-id="82d22-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="82d22-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="82d22-204">Tschechien</span><span class="sxs-lookup"><span data-stu-id="82d22-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="82d22-205">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-205">Format</span></span>

<span data-ttu-id="82d22-206">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-207">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-207">Pattern</span></span>

<span data-ttu-id="82d22-208">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="82d22-209">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-209">Checksum</span></span>

<span data-ttu-id="82d22-210">No</span><span class="sxs-lookup"><span data-stu-id="82d22-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-211">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-211">Definition</span></span>

<span data-ttu-id="82d22-212">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-213">Der reguläre Ausdruck `Regex_czech_republic_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-214">Ein Schlüsselwort `Keywords_czech_republic_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-215">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-215">Keywords</span></span>

<span data-ttu-id="82d22-216">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-216"></span></span>
|<span data-ttu-id="82d22-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-218">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-218">passport number</span></span>  <br/> <span data-ttu-id="82d22-219">Tschechische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-219">czech passport number</span></span>  <br/> <span data-ttu-id="82d22-220">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-220">passport no</span></span>  <br/> <span data-ttu-id="82d22-221">Cestovní Pas</span><span class="sxs-lookup"><span data-stu-id="82d22-221">cestovní pas</span></span>  <br/> <span data-ttu-id="82d22-222">Pas</span><span class="sxs-lookup"><span data-stu-id="82d22-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="82d22-223">Dänemark</span><span class="sxs-lookup"><span data-stu-id="82d22-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="82d22-224">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-224">Format</span></span>

<span data-ttu-id="82d22-225">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-226">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-226">Pattern</span></span>

 <span data-ttu-id="82d22-227">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="82d22-228">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-228">Checksum</span></span>

<span data-ttu-id="82d22-229">No</span><span class="sxs-lookup"><span data-stu-id="82d22-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-230">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-230">Definition</span></span>

<span data-ttu-id="82d22-231">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-232">Der reguläre Ausdruck `Regex_denmark_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-233">Ein Schlüsselwort `Keywords_denmark_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-234">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-234">Keywords</span></span>

<span data-ttu-id="82d22-235">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-235"></span></span>
|<span data-ttu-id="82d22-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-237">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-237">passport number</span></span>  <br/> <span data-ttu-id="82d22-238">dänische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-238">danish passport number</span></span>  <br/> <span data-ttu-id="82d22-239">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-239">passport no</span></span>  <br/> <span data-ttu-id="82d22-240">Pas</span><span class="sxs-lookup"><span data-stu-id="82d22-240">pas</span></span>  <br/> <span data-ttu-id="82d22-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="82d22-242">Estland</span><span class="sxs-lookup"><span data-stu-id="82d22-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="82d22-243">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-243">Format</span></span>

<span data-ttu-id="82d22-244">Ein Buchstabe, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-245">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-245">Pattern</span></span>

<span data-ttu-id="82d22-246">Ein Buchstabe, gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="82d22-247">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-247">Checksum</span></span>

<span data-ttu-id="82d22-248">No</span><span class="sxs-lookup"><span data-stu-id="82d22-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-249">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-249">Definition</span></span>

<span data-ttu-id="82d22-250">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-251">Der reguläre Ausdruck `Regex_estonia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-252">Ein Schlüsselwort `Keywords_estonia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-253">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-253">Keywords</span></span>

<span data-ttu-id="82d22-254">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-254"></span></span>
|<span data-ttu-id="82d22-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-256">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-256">passport number</span></span>  <br/> <span data-ttu-id="82d22-257">Estnische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-257">estonian passport number</span></span>  <br/> <span data-ttu-id="82d22-258">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-258">passport no</span></span>  <br/> <span data-ttu-id="82d22-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="82d22-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="82d22-260">Finnland</span><span class="sxs-lookup"><span data-stu-id="82d22-260">Finland</span></span>

<span data-ttu-id="82d22-261">Ausführliche Informationen finden Sie im Abschnitt "Finnland-Passport-Nummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="82d22-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="82d22-262">Frankreich</span><span class="sxs-lookup"><span data-stu-id="82d22-262">France</span></span>

<span data-ttu-id="82d22-263">Ausführliche Informationen finden Sie im Abschnitt "französische Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="82d22-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="82d22-264">Deutschland</span><span class="sxs-lookup"><span data-stu-id="82d22-264">Germany</span></span>

<span data-ttu-id="82d22-265">Ausführliche Informationen finden Sie im Abschnitt "Deutschland Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="82d22-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="82d22-266">Griechenland</span><span class="sxs-lookup"><span data-stu-id="82d22-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="82d22-267">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-267">Format</span></span>

<span data-ttu-id="82d22-268">Zwei Buchstaben, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-269">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-269">Pattern</span></span>

<span data-ttu-id="82d22-270">Zwei Buchstaben gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="82d22-271">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-271">Checksum</span></span>

<span data-ttu-id="82d22-272">No</span><span class="sxs-lookup"><span data-stu-id="82d22-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-273">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-273">Definition</span></span>

<span data-ttu-id="82d22-274">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-275">Der reguläre Ausdruck `Regex_greece_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-276">Ein Schlüsselwort `Keywords_greece_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-277">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-277">Keywords</span></span>

<span data-ttu-id="82d22-278">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-278"></span></span>
|<span data-ttu-id="82d22-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-280">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-280">passport number</span></span>  <br/> <span data-ttu-id="82d22-281">griechische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-281">greek passport number</span></span>  <br/> <span data-ttu-id="82d22-282">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-282">passport no</span></span>  <br/> <span data-ttu-id="82d22-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="82d22-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="82d22-284">Ungarn</span><span class="sxs-lookup"><span data-stu-id="82d22-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="82d22-285">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-285">Format</span></span>

<span data-ttu-id="82d22-286">Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-287">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-287">Pattern</span></span>

<span data-ttu-id="82d22-288">Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="82d22-289">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-289">Checksum</span></span>

<span data-ttu-id="82d22-290">No</span><span class="sxs-lookup"><span data-stu-id="82d22-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-291">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-291">Definition</span></span>

<span data-ttu-id="82d22-292">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-293">Der reguläre Ausdruck `Regex_hungary_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-294">Ein Schlüsselwort `Keywords_hungary_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-295">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-295">Keywords</span></span>

<span data-ttu-id="82d22-296">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-296"></span></span>
|<span data-ttu-id="82d22-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-298">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-298">passport number</span></span>  <br/> <span data-ttu-id="82d22-299">ungarische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="82d22-300">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-300">passport no</span></span>  <br/> <span data-ttu-id="82d22-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="82d22-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="82d22-302">Irland</span><span class="sxs-lookup"><span data-stu-id="82d22-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="82d22-303">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-303">Format</span></span>

<span data-ttu-id="82d22-304">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-305">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-305">Pattern</span></span>

<span data-ttu-id="82d22-306">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="82d22-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="82d22-307">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="82d22-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="82d22-308">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="82d22-309">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-309">Checksum</span></span>

<span data-ttu-id="82d22-310">No</span><span class="sxs-lookup"><span data-stu-id="82d22-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-311">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-311">Definition</span></span>

<span data-ttu-id="82d22-312">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-313">Der reguläre Ausdruck `Regex_ireland_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-314">Ein Schlüsselwort `Keywords_ireland_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-315">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-315">Keywords</span></span>

<span data-ttu-id="82d22-316">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-316"></span></span>
|<span data-ttu-id="82d22-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-318">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-318">passport number</span></span>  <br/> <span data-ttu-id="82d22-319">irische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-319">irish passport number</span></span>  <br/> <span data-ttu-id="82d22-320">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-320">passport no</span></span>  <br/> <span data-ttu-id="82d22-321">Pas</span><span class="sxs-lookup"><span data-stu-id="82d22-321">pas</span></span>  <br/> <span data-ttu-id="82d22-322">Pass</span><span class="sxs-lookup"><span data-stu-id="82d22-322">passport</span></span>  <br/> <span data-ttu-id="82d22-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="82d22-323">passeport</span></span>  <br/> <span data-ttu-id="82d22-324">Passeport numero</span><span class="sxs-lookup"><span data-stu-id="82d22-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="82d22-325">Italien</span><span class="sxs-lookup"><span data-stu-id="82d22-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="82d22-326">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-326">Format</span></span>

<span data-ttu-id="82d22-327">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-328">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-328">Pattern</span></span>

<span data-ttu-id="82d22-329">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="82d22-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="82d22-330">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="82d22-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="82d22-331">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="82d22-332">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-332">Checksum</span></span>

<span data-ttu-id="82d22-333">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="82d22-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-334">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-334">Definition</span></span>

<span data-ttu-id="82d22-335">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-336">Der reguläre Ausdruck `Regex_italy_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-337">Ein Schlüsselwort `Keywords_italy_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-338">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-338">Keywords</span></span>

<span data-ttu-id="82d22-339">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-339"></span></span>
|<span data-ttu-id="82d22-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-341">italienische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-341">italian passport number</span></span>  <br/> <span data-ttu-id="82d22-342">Repubblica Italiana Passa Porto</span><span class="sxs-lookup"><span data-stu-id="82d22-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="82d22-343">Passa Porto</span><span class="sxs-lookup"><span data-stu-id="82d22-343">passaporto</span></span>  <br/> <span data-ttu-id="82d22-344">Passa Porto Italiana</span><span class="sxs-lookup"><span data-stu-id="82d22-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="82d22-345">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-345">passport number</span></span>  <br/> <span data-ttu-id="82d22-346">Italiana Passa Porto numero</span><span class="sxs-lookup"><span data-stu-id="82d22-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="82d22-347">Passa Porto numero</span><span class="sxs-lookup"><span data-stu-id="82d22-347">passaporto numero</span></span>  <br/> <span data-ttu-id="82d22-348">Numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="82d22-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="82d22-349">Numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="82d22-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="82d22-350">Lettland</span><span class="sxs-lookup"><span data-stu-id="82d22-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="82d22-351">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-351">Format</span></span>

<span data-ttu-id="82d22-352">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-353">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-353">Pattern</span></span>

<span data-ttu-id="82d22-354">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="82d22-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="82d22-355">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="82d22-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="82d22-356">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="82d22-357">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-357">Checksum</span></span>

<span data-ttu-id="82d22-358">No</span><span class="sxs-lookup"><span data-stu-id="82d22-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-359">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-359">Definition</span></span>

<span data-ttu-id="82d22-360">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-361">Der reguläre Ausdruck `Regex_latvia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-362">Ein Schlüsselwort `Keywords_latvia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-363">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-363">Keywords</span></span>

<span data-ttu-id="82d22-364">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-364"></span></span>
|<span data-ttu-id="82d22-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-366">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-366">passport number</span></span>  <br/> <span data-ttu-id="82d22-367">Lettische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-367">latvian passport number</span></span>  <br/> <span data-ttu-id="82d22-368">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-368">passport no</span></span>  <br/> <span data-ttu-id="82d22-369">Pase numurs</span><span class="sxs-lookup"><span data-stu-id="82d22-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="82d22-370">Litauen</span><span class="sxs-lookup"><span data-stu-id="82d22-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="82d22-371">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-371">Format</span></span>

<span data-ttu-id="82d22-372">Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-373">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-373">Pattern</span></span>

<span data-ttu-id="82d22-374">Acht Ziffern oder Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="82d22-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="82d22-375">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-375">Checksum</span></span>

<span data-ttu-id="82d22-376">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="82d22-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-377">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-377">Definition</span></span>

<span data-ttu-id="82d22-378">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-379">Der reguläre Ausdruck `Regex_lithuania_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-380">Ein Schlüsselwort `Keywords_lithuania_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-381">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-381">Keywords</span></span>

<span data-ttu-id="82d22-382">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-382"></span></span>
|<span data-ttu-id="82d22-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-384">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-384">passport number</span></span>  <br/> <span data-ttu-id="82d22-385">lithunian Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="82d22-386">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-386">passport no</span></span>  <br/> <span data-ttu-id="82d22-387">Paso Numeris</span><span class="sxs-lookup"><span data-stu-id="82d22-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="82d22-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="82d22-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="82d22-389">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-389">Format</span></span>

<span data-ttu-id="82d22-390">Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-391">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-391">Pattern</span></span>

<span data-ttu-id="82d22-392">Acht Ziffern oder Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="82d22-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="82d22-393">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-393">Checksum</span></span>

<span data-ttu-id="82d22-394">No</span><span class="sxs-lookup"><span data-stu-id="82d22-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-395">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-395">Definition</span></span>

<span data-ttu-id="82d22-396">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-397">Der reguläre Ausdruck `Regex_nation_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-398">Ein Schlüsselwort `Keywords_nation_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-399">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-399">Keywords</span></span>

<span data-ttu-id="82d22-400">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-400"></span></span>
|<span data-ttu-id="82d22-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-402">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-402">passport number</span></span>  <br/> <span data-ttu-id="82d22-403">Lettische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-403">latvian passport number</span></span>  <br/> <span data-ttu-id="82d22-404">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-404">passport no</span></span>  <br/> <span data-ttu-id="82d22-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="82d22-406">Malta</span><span class="sxs-lookup"><span data-stu-id="82d22-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="82d22-407">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-407">Format</span></span>

<span data-ttu-id="82d22-408">Sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-409">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-409">Pattern</span></span>

 <span data-ttu-id="82d22-410">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="82d22-411">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-411">Checksum</span></span>

<span data-ttu-id="82d22-412">No</span><span class="sxs-lookup"><span data-stu-id="82d22-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-413">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-413">Definition</span></span>

<span data-ttu-id="82d22-414">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-415">Der reguläre Ausdruck `Regex_malta_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-416">Ein Schlüsselwort `Keywords_malta_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-417">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-417">Keywords</span></span>

<span data-ttu-id="82d22-418">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-418"></span></span>
|<span data-ttu-id="82d22-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-420">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-420">passport number</span></span>  <br/> <span data-ttu-id="82d22-421">Maltesische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-421">maltese passport number</span></span>  <br/> <span data-ttu-id="82d22-422">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-422">passport no</span></span>  <br/> <span data-ttu-id="82d22-423">numru Tal-Passaport</span><span class="sxs-lookup"><span data-stu-id="82d22-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="82d22-424">Niederlande</span><span class="sxs-lookup"><span data-stu-id="82d22-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="82d22-425">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-425">Format</span></span>

<span data-ttu-id="82d22-426">Neun Buchstaben oder Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-427">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-427">Pattern</span></span>

<span data-ttu-id="82d22-428">Neun Buchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="82d22-429">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-429">Checksum</span></span>

<span data-ttu-id="82d22-430">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="82d22-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-431">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-431">Definition</span></span>

<span data-ttu-id="82d22-432">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-433">Der reguläre Ausdruck `Regex_netherlands_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-434">Ein Schlüsselwort `Keywords_netherlands_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-435">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-435">Keywords</span></span>

<span data-ttu-id="82d22-436">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-436"></span></span>
|<span data-ttu-id="82d22-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-438">niederländische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-438">dutch passport number</span></span>  <br/> <span data-ttu-id="82d22-439">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-439">passport number</span></span>  <br/> <span data-ttu-id="82d22-440">niederländische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="82d22-441">Nederlanden paspoort Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="82d22-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="82d22-442">paspoort</span></span>  <br/> <span data-ttu-id="82d22-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="82d22-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="82d22-445">Polen</span><span class="sxs-lookup"><span data-stu-id="82d22-445">Poland</span></span>

<span data-ttu-id="82d22-446">Ausführliche Informationen finden Sie im Abschnitt "Polen-Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="82d22-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="82d22-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="82d22-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="82d22-448">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-448">Format</span></span>

<span data-ttu-id="82d22-449">Ein Buchstabe, gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-450">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-450">Pattern</span></span>

<span data-ttu-id="82d22-451">Ein Buchstabe, gefolgt von sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="82d22-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="82d22-452">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="82d22-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="82d22-453">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="82d22-454">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-454">Checksum</span></span>

<span data-ttu-id="82d22-455">No</span><span class="sxs-lookup"><span data-stu-id="82d22-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-456">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-456">Definition</span></span>

<span data-ttu-id="82d22-457">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-458">Der reguläre Ausdruck `Regex_portugal_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-459">Ein Schlüsselwort `Keywords_portugal_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-460">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-460">Keywords</span></span>

<span data-ttu-id="82d22-461">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-461"></span></span>
|<span data-ttu-id="82d22-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-463">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-463">passport number</span></span>  <br/> <span data-ttu-id="82d22-464">portugiesische Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="82d22-465">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-465">passport no</span></span>  <br/> <span data-ttu-id="82d22-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="82d22-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="82d22-467">Rumänien</span><span class="sxs-lookup"><span data-stu-id="82d22-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="82d22-468">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-468">Format</span></span>

<span data-ttu-id="82d22-469">Acht oder neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-470">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-470">Pattern</span></span>

<span data-ttu-id="82d22-471">Acht oder neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="82d22-472">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-472">Checksum</span></span>

<span data-ttu-id="82d22-473">No</span><span class="sxs-lookup"><span data-stu-id="82d22-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-474">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-474">Definition</span></span>

<span data-ttu-id="82d22-475">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-476">Der reguläre Ausdruck `Regex_romania_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-477">Ein Schlüsselwort `Keywords_romania_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-478">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-478">Keywords</span></span>

<span data-ttu-id="82d22-479">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-479"></span></span>
|<span data-ttu-id="82d22-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-481">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-481">passport number</span></span>  <br/> <span data-ttu-id="82d22-482">rumänische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-482">romanian passport number</span></span>  <br/> <span data-ttu-id="82d22-483">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-483">passport no</span></span>  <br/> <span data-ttu-id="82d22-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="82d22-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="82d22-485">Slowakei</span><span class="sxs-lookup"><span data-stu-id="82d22-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="82d22-486">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-486">Format</span></span>

<span data-ttu-id="82d22-487">Eine Ziffer oder ein Buchstabe, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-488">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-488">Pattern</span></span>

<span data-ttu-id="82d22-489">Eine Ziffer oder ein Buchstabe (ohne Groß-/Kleinschreibung), gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="82d22-490">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-490">Checksum</span></span>

<span data-ttu-id="82d22-491">No</span><span class="sxs-lookup"><span data-stu-id="82d22-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-492">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-492">Definition</span></span>

<span data-ttu-id="82d22-493">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-494">Der reguläre Ausdruck `Regex_slovakia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-495">Ein Schlüsselwort `Keywords_slovakia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-496">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-496">Keywords</span></span>

<span data-ttu-id="82d22-497">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-497"></span></span>
|<span data-ttu-id="82d22-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-499">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-499">passport number</span></span>  <br/> <span data-ttu-id="82d22-500">Slowakische Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="82d22-501">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-501">passport no</span></span>  <br/> <span data-ttu-id="82d22-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="82d22-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="82d22-503">Slowenien</span><span class="sxs-lookup"><span data-stu-id="82d22-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="82d22-504">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-504">Format</span></span>

<span data-ttu-id="82d22-505">Zwei Buchstaben, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-506">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-506">Pattern</span></span>

<span data-ttu-id="82d22-507">Zwei Buchstaben, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="82d22-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="82d22-508">Der Buchstabe "P"</span><span class="sxs-lookup"><span data-stu-id="82d22-508">The letter "P"</span></span>
    
- <span data-ttu-id="82d22-509">Ein Großbuchstabe</span><span class="sxs-lookup"><span data-stu-id="82d22-509">One uppercase letter</span></span>
    
- <span data-ttu-id="82d22-510">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="82d22-511">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-511">Checksum</span></span>

<span data-ttu-id="82d22-512">No</span><span class="sxs-lookup"><span data-stu-id="82d22-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-513">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-513">Definition</span></span>

<span data-ttu-id="82d22-514">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-515">Der reguläre Ausdruck `Regex_slovenia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-516">Ein Schlüsselwort `Keywords_slovenia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-517">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-517">Keywords</span></span>

<span data-ttu-id="82d22-518">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-518"></span></span>
|<span data-ttu-id="82d22-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-520">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-520">passport number</span></span>  <br/> <span data-ttu-id="82d22-521">slowenische Passnummer</span><span class="sxs-lookup"><span data-stu-id="82d22-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="82d22-522">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-522">passport no</span></span>  <br/> <span data-ttu-id="82d22-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="82d22-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="82d22-524">Spanien</span><span class="sxs-lookup"><span data-stu-id="82d22-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="82d22-525">Format</span><span class="sxs-lookup"><span data-stu-id="82d22-525">Format</span></span>

<span data-ttu-id="82d22-526">Eine Kombination aus Buchstaben und Zahlen mit acht oder neun Zeichen ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="82d22-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="82d22-527">Muster</span><span class="sxs-lookup"><span data-stu-id="82d22-527">Pattern</span></span>

<span data-ttu-id="82d22-528">Eine Kombination aus Buchstaben und Zahlen aus acht oder neun Zeichen:</span><span class="sxs-lookup"><span data-stu-id="82d22-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="82d22-529">Zwei Ziffern oder Buchstaben</span><span class="sxs-lookup"><span data-stu-id="82d22-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="82d22-530">Eine Ziffer oder ein Buchstabe (optional)</span><span class="sxs-lookup"><span data-stu-id="82d22-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="82d22-531">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="82d22-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="82d22-532">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="82d22-532">Checksum</span></span>

<span data-ttu-id="82d22-533">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="82d22-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="82d22-534">Definition</span><span class="sxs-lookup"><span data-stu-id="82d22-534">Definition</span></span>

<span data-ttu-id="82d22-535">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82d22-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="82d22-536">Der reguläre Ausdruck `Regex_spain_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82d22-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="82d22-537">Ein Schlüsselwort `Keywords_spain_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="82d22-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="82d22-538">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82d22-538">Keywords</span></span>

<span data-ttu-id="82d22-539">| |</span><span class="sxs-lookup"><span data-stu-id="82d22-539"></span></span>
|<span data-ttu-id="82d22-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="82d22-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="82d22-541">Pass</span><span class="sxs-lookup"><span data-stu-id="82d22-541">passport</span></span>  <br/> <span data-ttu-id="82d22-542">Spanien-Passport</span><span class="sxs-lookup"><span data-stu-id="82d22-542">spain passport</span></span>  <br/> <span data-ttu-id="82d22-543">Passport-Buch</span><span class="sxs-lookup"><span data-stu-id="82d22-543">passport book</span></span>  <br/> <span data-ttu-id="82d22-544">passport number</span><span class="sxs-lookup"><span data-stu-id="82d22-544">passport number</span></span>  <br/> <span data-ttu-id="82d22-545">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="82d22-545">passport no</span></span>  <br/> <span data-ttu-id="82d22-546">Libreta Pasaporte</span><span class="sxs-lookup"><span data-stu-id="82d22-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="82d22-547">número Pasaporte</span><span class="sxs-lookup"><span data-stu-id="82d22-547">número pasaporte</span></span>  <br/> <span data-ttu-id="82d22-548">ESPAÑA PASAPORTE</span><span class="sxs-lookup"><span data-stu-id="82d22-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="82d22-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="82d22-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="82d22-550">Schweden</span><span class="sxs-lookup"><span data-stu-id="82d22-550">Sweden</span></span>

<span data-ttu-id="82d22-551">Ausführliche Informationen finden Sie im Abschnitt "schwedische Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="82d22-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="82d22-552">UK</span><span class="sxs-lookup"><span data-stu-id="82d22-552">UK</span></span>

<span data-ttu-id="82d22-553">Ausführliche Informationen finden Sie im Abschnitt "U.S./U.K.</span><span class="sxs-lookup"><span data-stu-id="82d22-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="82d22-554">Passport-Nummer "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="82d22-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="82d22-555">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82d22-555">See also</span></span>

[<span data-ttu-id="82d22-556">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="82d22-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

