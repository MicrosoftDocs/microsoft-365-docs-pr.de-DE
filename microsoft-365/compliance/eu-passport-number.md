---
title: EU-Passport-Nummer
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp EU-Passport-Nummern erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: 4afcf7b764eb8976e0588464515256f7cb1bdb8d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805948"
---
# <a name="eu-passport-number"></a><span data-ttu-id="25414-104">EU-Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-104">EU Passport Number</span></span>

<span data-ttu-id="25414-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp EU-Passport-Nummern erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="25414-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="25414-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="25414-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="25414-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="25414-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="25414-108">Format</span><span class="sxs-lookup"><span data-stu-id="25414-108">Format</span></span>

<span data-ttu-id="25414-109">Ein Buchstabe, gefolgt von einem optionalen Leerzeichen und sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-110">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-110">Pattern</span></span>

<span data-ttu-id="25414-111">Eine Kombination aus einem Buchstaben, sieben Ziffern und einem Leerzeichen:</span><span class="sxs-lookup"><span data-stu-id="25414-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="25414-112">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="25414-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="25414-113">Ein Leerzeichen (optional)</span><span class="sxs-lookup"><span data-stu-id="25414-113">One space (optional)</span></span>
    
- <span data-ttu-id="25414-114">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="25414-115">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-115">Checksum</span></span>

<span data-ttu-id="25414-116">Nicht anwendbar</span><span class="sxs-lookup"><span data-stu-id="25414-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-117">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-117">Definition</span></span>

<span data-ttu-id="25414-118">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-119">Der reguläre Ausdruck `Regex_austria_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-120">Ein Schlüsselwort `Keywords_austria_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-121">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-121">Keywords</span></span>

<span data-ttu-id="25414-122">| |</span><span class="sxs-lookup"><span data-stu-id="25414-122"></span></span>
|<span data-ttu-id="25414-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-124">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-124">passport number</span></span>  <br/> <span data-ttu-id="25414-125">Österreichische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-125">austrian passport number</span></span>  <br/> <span data-ttu-id="25414-126">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-126">passport no</span></span>  <br/> <span data-ttu-id="25414-127">Reisepass</span><span class="sxs-lookup"><span data-stu-id="25414-127">reisepass</span></span>  <br/> <span data-ttu-id="25414-128">österreichisch Reisepass</span><span class="sxs-lookup"><span data-stu-id="25414-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="25414-129">Belgien</span><span class="sxs-lookup"><span data-stu-id="25414-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="25414-130">Format</span><span class="sxs-lookup"><span data-stu-id="25414-130">Format</span></span>

<span data-ttu-id="25414-131">Zwei Buchstaben, gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-132">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-132">Pattern</span></span>

<span data-ttu-id="25414-133">Zwei Buchstaben und gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="25414-134">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-134">Checksum</span></span>

<span data-ttu-id="25414-135">Nicht anwendbar</span><span class="sxs-lookup"><span data-stu-id="25414-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-136">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-136">Definition</span></span>

<span data-ttu-id="25414-137">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-138">Der reguläre Ausdruck `Regex_belgium_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-139">Ein Schlüsselwort `Keywords_belgium_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-140">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-140">Keywords</span></span>

<span data-ttu-id="25414-141">| |</span><span class="sxs-lookup"><span data-stu-id="25414-141"></span></span>
|<span data-ttu-id="25414-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-143">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-143">passport number</span></span>  <br/> <span data-ttu-id="25414-144">belgische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-144">belgian passport number</span></span>  <br/> <span data-ttu-id="25414-145">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-145">passport no</span></span>  <br/> <span data-ttu-id="25414-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="25414-146">paspoort</span></span>  <br/> <span data-ttu-id="25414-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="25414-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="25414-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="25414-148">reisepass kein</span></span>  <br/> <span data-ttu-id="25414-149">Reisepass</span><span class="sxs-lookup"><span data-stu-id="25414-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="25414-150">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="25414-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="25414-151">Format</span><span class="sxs-lookup"><span data-stu-id="25414-151">Format</span></span>

<span data-ttu-id="25414-152">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-153">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-153">Pattern</span></span>

 <span data-ttu-id="25414-154">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="25414-155">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-155">Checksum</span></span>

<span data-ttu-id="25414-156">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-157">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-157">Definition</span></span>

<span data-ttu-id="25414-158">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-159">Der reguläre Ausdruck `Regex_bulgaria_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-160">Ein Schlüsselwort `Keywords_bulgaria_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-161">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-161">Keywords</span></span>

<span data-ttu-id="25414-162">| |</span><span class="sxs-lookup"><span data-stu-id="25414-162"></span></span>
|<span data-ttu-id="25414-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-164">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-164">passport number</span></span>  <br/> <span data-ttu-id="25414-165">Bulgarische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="25414-166">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-166">passport no</span></span>  <br/> <span data-ttu-id="25414-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="25414-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="25414-168">Kroatien</span><span class="sxs-lookup"><span data-stu-id="25414-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="25414-169">Format</span><span class="sxs-lookup"><span data-stu-id="25414-169">Format</span></span>

<span data-ttu-id="25414-170">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-171">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-171">Pattern</span></span>

 <span data-ttu-id="25414-172">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="25414-173">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-173">Checksum</span></span>

<span data-ttu-id="25414-174">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-175">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-175">Definition</span></span>

<span data-ttu-id="25414-176">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-177">Der reguläre Ausdruck `Regex_croatia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-178">Ein Schlüsselwort `Keywords_croatia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-179">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-179">Keywords</span></span>

<span data-ttu-id="25414-180">| |</span><span class="sxs-lookup"><span data-stu-id="25414-180"></span></span>
|<span data-ttu-id="25414-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-182">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-182">passport number</span></span>  <br/> <span data-ttu-id="25414-183">Kroatische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-183">croatian passport number</span></span>  <br/> <span data-ttu-id="25414-184">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-184">passport no</span></span>  <br/> <span data-ttu-id="25414-185">Broj putovnice</span><span class="sxs-lookup"><span data-stu-id="25414-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="25414-186">Zypern</span><span class="sxs-lookup"><span data-stu-id="25414-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="25414-187">Format</span><span class="sxs-lookup"><span data-stu-id="25414-187">Format</span></span>

<span data-ttu-id="25414-188">Ein Buchstabe, gefolgt von 6-8 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-189">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-189">Pattern</span></span>

<span data-ttu-id="25414-190">Ein Buchstabe, gefolgt von sechs bis acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="25414-191">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-191">Checksum</span></span>

<span data-ttu-id="25414-192">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-193">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-193">Definition</span></span>

<span data-ttu-id="25414-194">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-195">Der reguläre Ausdruck `Regex_cyprus_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-196">Ein Schlüsselwort `Keywords_cyprus_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-197">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-197">Keywords</span></span>

<span data-ttu-id="25414-198">| |</span><span class="sxs-lookup"><span data-stu-id="25414-198"></span></span>
|<span data-ttu-id="25414-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-200">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-200">passport number</span></span>  <br/> <span data-ttu-id="25414-201">Zypern-Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="25414-202">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-202">passport no</span></span>  <br/> <span data-ttu-id="25414-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="25414-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="25414-204">Tschechien</span><span class="sxs-lookup"><span data-stu-id="25414-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="25414-205">Format</span><span class="sxs-lookup"><span data-stu-id="25414-205">Format</span></span>

<span data-ttu-id="25414-206">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-207">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-207">Pattern</span></span>

<span data-ttu-id="25414-208">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="25414-209">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-209">Checksum</span></span>

<span data-ttu-id="25414-210">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-211">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-211">Definition</span></span>

<span data-ttu-id="25414-212">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-213">Der reguläre Ausdruck `Regex_czech_republic_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-214">Ein Schlüsselwort `Keywords_czech_republic_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-215">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-215">Keywords</span></span>

<span data-ttu-id="25414-216">| |</span><span class="sxs-lookup"><span data-stu-id="25414-216"></span></span>
|<span data-ttu-id="25414-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-218">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-218">passport number</span></span>  <br/> <span data-ttu-id="25414-219">Tschechische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-219">czech passport number</span></span>  <br/> <span data-ttu-id="25414-220">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-220">passport no</span></span>  <br/> <span data-ttu-id="25414-221">Cestovní Pas</span><span class="sxs-lookup"><span data-stu-id="25414-221">cestovní pas</span></span>  <br/> <span data-ttu-id="25414-222">Pas</span><span class="sxs-lookup"><span data-stu-id="25414-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="25414-223">Dänemark</span><span class="sxs-lookup"><span data-stu-id="25414-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="25414-224">Format</span><span class="sxs-lookup"><span data-stu-id="25414-224">Format</span></span>

<span data-ttu-id="25414-225">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-226">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-226">Pattern</span></span>

 <span data-ttu-id="25414-227">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="25414-228">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-228">Checksum</span></span>

<span data-ttu-id="25414-229">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-230">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-230">Definition</span></span>

<span data-ttu-id="25414-231">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-232">Der reguläre Ausdruck `Regex_denmark_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-233">Ein Schlüsselwort `Keywords_denmark_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-234">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-234">Keywords</span></span>

<span data-ttu-id="25414-235">| |</span><span class="sxs-lookup"><span data-stu-id="25414-235"></span></span>
|<span data-ttu-id="25414-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-237">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-237">passport number</span></span>  <br/> <span data-ttu-id="25414-238">dänische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-238">danish passport number</span></span>  <br/> <span data-ttu-id="25414-239">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-239">passport no</span></span>  <br/> <span data-ttu-id="25414-240">Pas</span><span class="sxs-lookup"><span data-stu-id="25414-240">pas</span></span>  <br/> <span data-ttu-id="25414-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="25414-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="25414-242">Estland</span><span class="sxs-lookup"><span data-stu-id="25414-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="25414-243">Format</span><span class="sxs-lookup"><span data-stu-id="25414-243">Format</span></span>

<span data-ttu-id="25414-244">Ein Buchstabe, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-245">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-245">Pattern</span></span>

<span data-ttu-id="25414-246">Ein Buchstabe, gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="25414-247">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-247">Checksum</span></span>

<span data-ttu-id="25414-248">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-249">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-249">Definition</span></span>

<span data-ttu-id="25414-250">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-251">Der reguläre Ausdruck `Regex_estonia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-252">Ein Schlüsselwort `Keywords_estonia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-253">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-253">Keywords</span></span>

<span data-ttu-id="25414-254">| |</span><span class="sxs-lookup"><span data-stu-id="25414-254"></span></span>
|<span data-ttu-id="25414-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-256">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-256">passport number</span></span>  <br/> <span data-ttu-id="25414-257">Estnische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-257">estonian passport number</span></span>  <br/> <span data-ttu-id="25414-258">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-258">passport no</span></span>  <br/> <span data-ttu-id="25414-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="25414-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="25414-260">Finnland</span><span class="sxs-lookup"><span data-stu-id="25414-260">Finland</span></span>

<span data-ttu-id="25414-261">Ausführliche Informationen finden Sie im Abschnitt "Finnland-Passport-Nummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="25414-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="25414-262">Frankreich</span><span class="sxs-lookup"><span data-stu-id="25414-262">France</span></span>

<span data-ttu-id="25414-263">Ausführliche Informationen finden Sie im Abschnitt "französische Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="25414-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="25414-264">Deutschland</span><span class="sxs-lookup"><span data-stu-id="25414-264">Germany</span></span>

<span data-ttu-id="25414-265">Ausführliche Informationen finden Sie im Abschnitt "Deutsche Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="25414-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="25414-266">Griechenland</span><span class="sxs-lookup"><span data-stu-id="25414-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="25414-267">Format</span><span class="sxs-lookup"><span data-stu-id="25414-267">Format</span></span>

<span data-ttu-id="25414-268">Zwei Buchstaben, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-269">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-269">Pattern</span></span>

<span data-ttu-id="25414-270">Zwei Buchstaben gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="25414-271">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-271">Checksum</span></span>

<span data-ttu-id="25414-272">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-273">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-273">Definition</span></span>

<span data-ttu-id="25414-274">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-275">Der reguläre Ausdruck `Regex_greece_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-276">Ein Schlüsselwort `Keywords_greece_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-277">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-277">Keywords</span></span>

<span data-ttu-id="25414-278">| |</span><span class="sxs-lookup"><span data-stu-id="25414-278"></span></span>
|<span data-ttu-id="25414-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-280">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-280">passport number</span></span>  <br/> <span data-ttu-id="25414-281">griechische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-281">greek passport number</span></span>  <br/> <span data-ttu-id="25414-282">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-282">passport no</span></span>  <br/> <span data-ttu-id="25414-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="25414-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="25414-284">Ungarn</span><span class="sxs-lookup"><span data-stu-id="25414-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="25414-285">Format</span><span class="sxs-lookup"><span data-stu-id="25414-285">Format</span></span>

<span data-ttu-id="25414-286">Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-287">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-287">Pattern</span></span>

<span data-ttu-id="25414-288">Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="25414-289">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-289">Checksum</span></span>

<span data-ttu-id="25414-290">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-291">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-291">Definition</span></span>

<span data-ttu-id="25414-292">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-293">Der reguläre Ausdruck `Regex_hungary_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-294">Ein Schlüsselwort `Keywords_hungary_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-295">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-295">Keywords</span></span>

<span data-ttu-id="25414-296">| |</span><span class="sxs-lookup"><span data-stu-id="25414-296"></span></span>
|<span data-ttu-id="25414-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-298">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-298">passport number</span></span>  <br/> <span data-ttu-id="25414-299">ungarische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="25414-300">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-300">passport no</span></span>  <br/> <span data-ttu-id="25414-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="25414-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="25414-302">Irland</span><span class="sxs-lookup"><span data-stu-id="25414-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="25414-303">Format</span><span class="sxs-lookup"><span data-stu-id="25414-303">Format</span></span>

<span data-ttu-id="25414-304">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-305">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-305">Pattern</span></span>

<span data-ttu-id="25414-306">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="25414-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="25414-307">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="25414-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="25414-308">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="25414-309">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-309">Checksum</span></span>

<span data-ttu-id="25414-310">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-311">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-311">Definition</span></span>

<span data-ttu-id="25414-312">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-313">Der reguläre Ausdruck `Regex_ireland_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-314">Ein Schlüsselwort `Keywords_ireland_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-315">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-315">Keywords</span></span>

<span data-ttu-id="25414-316">| |</span><span class="sxs-lookup"><span data-stu-id="25414-316"></span></span>
|<span data-ttu-id="25414-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-318">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-318">passport number</span></span>  <br/> <span data-ttu-id="25414-319">irische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-319">irish passport number</span></span>  <br/> <span data-ttu-id="25414-320">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-320">passport no</span></span>  <br/> <span data-ttu-id="25414-321">Pas</span><span class="sxs-lookup"><span data-stu-id="25414-321">pas</span></span>  <br/> <span data-ttu-id="25414-322">Pass</span><span class="sxs-lookup"><span data-stu-id="25414-322">passport</span></span>  <br/> <span data-ttu-id="25414-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="25414-323">passeport</span></span>  <br/> <span data-ttu-id="25414-324">Passeport numero</span><span class="sxs-lookup"><span data-stu-id="25414-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="25414-325">Italien</span><span class="sxs-lookup"><span data-stu-id="25414-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="25414-326">Format</span><span class="sxs-lookup"><span data-stu-id="25414-326">Format</span></span>

<span data-ttu-id="25414-327">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-328">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-328">Pattern</span></span>

<span data-ttu-id="25414-329">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="25414-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="25414-330">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="25414-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="25414-331">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="25414-332">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-332">Checksum</span></span>

<span data-ttu-id="25414-333">Nicht anwendbar</span><span class="sxs-lookup"><span data-stu-id="25414-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-334">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-334">Definition</span></span>

<span data-ttu-id="25414-335">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-336">Der reguläre Ausdruck `Regex_italy_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-337">Ein Schlüsselwort `Keywords_italy_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-338">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-338">Keywords</span></span>

<span data-ttu-id="25414-339">| |</span><span class="sxs-lookup"><span data-stu-id="25414-339"></span></span>
|<span data-ttu-id="25414-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-341">italienische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-341">italian passport number</span></span>  <br/> <span data-ttu-id="25414-342">Repubblica Italiana Passa Porto</span><span class="sxs-lookup"><span data-stu-id="25414-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="25414-343">Passa Porto</span><span class="sxs-lookup"><span data-stu-id="25414-343">passaporto</span></span>  <br/> <span data-ttu-id="25414-344">Passa Porto Italiana</span><span class="sxs-lookup"><span data-stu-id="25414-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="25414-345">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-345">passport number</span></span>  <br/> <span data-ttu-id="25414-346">Italiana Passa Porto numero</span><span class="sxs-lookup"><span data-stu-id="25414-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="25414-347">Passa Porto numero</span><span class="sxs-lookup"><span data-stu-id="25414-347">passaporto numero</span></span>  <br/> <span data-ttu-id="25414-348">Numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="25414-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="25414-349">Numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="25414-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="25414-350">Lettland</span><span class="sxs-lookup"><span data-stu-id="25414-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="25414-351">Format</span><span class="sxs-lookup"><span data-stu-id="25414-351">Format</span></span>

<span data-ttu-id="25414-352">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-353">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-353">Pattern</span></span>

<span data-ttu-id="25414-354">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="25414-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="25414-355">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="25414-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="25414-356">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="25414-357">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-357">Checksum</span></span>

<span data-ttu-id="25414-358">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-359">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-359">Definition</span></span>

<span data-ttu-id="25414-360">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-361">Der reguläre Ausdruck `Regex_latvia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-362">Ein Schlüsselwort `Keywords_latvia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-363">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-363">Keywords</span></span>

<span data-ttu-id="25414-364">| |</span><span class="sxs-lookup"><span data-stu-id="25414-364"></span></span>
|<span data-ttu-id="25414-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-366">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-366">passport number</span></span>  <br/> <span data-ttu-id="25414-367">Lettische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-367">latvian passport number</span></span>  <br/> <span data-ttu-id="25414-368">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-368">passport no</span></span>  <br/> <span data-ttu-id="25414-369">Pase numurs</span><span class="sxs-lookup"><span data-stu-id="25414-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="25414-370">Litauen</span><span class="sxs-lookup"><span data-stu-id="25414-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="25414-371">Format</span><span class="sxs-lookup"><span data-stu-id="25414-371">Format</span></span>

<span data-ttu-id="25414-372">Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-373">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-373">Pattern</span></span>

<span data-ttu-id="25414-374">Acht Ziffern oder Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="25414-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="25414-375">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-375">Checksum</span></span>

<span data-ttu-id="25414-376">Nicht anwendbar</span><span class="sxs-lookup"><span data-stu-id="25414-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-377">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-377">Definition</span></span>

<span data-ttu-id="25414-378">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-379">Der reguläre Ausdruck `Regex_lithuania_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-380">Ein Schlüsselwort `Keywords_lithuania_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-381">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-381">Keywords</span></span>

<span data-ttu-id="25414-382">| |</span><span class="sxs-lookup"><span data-stu-id="25414-382"></span></span>
|<span data-ttu-id="25414-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-384">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-384">passport number</span></span>  <br/> <span data-ttu-id="25414-385">lithunian Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="25414-386">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-386">passport no</span></span>  <br/> <span data-ttu-id="25414-387">Paso Numeris</span><span class="sxs-lookup"><span data-stu-id="25414-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="25414-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="25414-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="25414-389">Format</span><span class="sxs-lookup"><span data-stu-id="25414-389">Format</span></span>

<span data-ttu-id="25414-390">Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-391">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-391">Pattern</span></span>

<span data-ttu-id="25414-392">Acht Ziffern oder Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="25414-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="25414-393">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-393">Checksum</span></span>

<span data-ttu-id="25414-394">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-395">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-395">Definition</span></span>

<span data-ttu-id="25414-396">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-397">Der reguläre Ausdruck `Regex_nation_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-398">Ein Schlüsselwort `Keywords_nation_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-399">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-399">Keywords</span></span>

<span data-ttu-id="25414-400">| |</span><span class="sxs-lookup"><span data-stu-id="25414-400"></span></span>
|<span data-ttu-id="25414-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-402">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-402">passport number</span></span>  <br/> <span data-ttu-id="25414-403">Lettische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-403">latvian passport number</span></span>  <br/> <span data-ttu-id="25414-404">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-404">passport no</span></span>  <br/> <span data-ttu-id="25414-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="25414-406">Malta</span><span class="sxs-lookup"><span data-stu-id="25414-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="25414-407">Format</span><span class="sxs-lookup"><span data-stu-id="25414-407">Format</span></span>

<span data-ttu-id="25414-408">Sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-409">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-409">Pattern</span></span>

 <span data-ttu-id="25414-410">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="25414-411">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-411">Checksum</span></span>

<span data-ttu-id="25414-412">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-413">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-413">Definition</span></span>

<span data-ttu-id="25414-414">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-415">Der reguläre Ausdruck `Regex_malta_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-416">Ein Schlüsselwort `Keywords_malta_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-417">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-417">Keywords</span></span>

<span data-ttu-id="25414-418">| |</span><span class="sxs-lookup"><span data-stu-id="25414-418"></span></span>
|<span data-ttu-id="25414-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-420">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-420">passport number</span></span>  <br/> <span data-ttu-id="25414-421">Maltesische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-421">maltese passport number</span></span>  <br/> <span data-ttu-id="25414-422">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-422">passport no</span></span>  <br/> <span data-ttu-id="25414-423">numru Tal-Passaport</span><span class="sxs-lookup"><span data-stu-id="25414-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="25414-424">Niederlande</span><span class="sxs-lookup"><span data-stu-id="25414-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="25414-425">Format</span><span class="sxs-lookup"><span data-stu-id="25414-425">Format</span></span>

<span data-ttu-id="25414-426">Neun Buchstaben oder Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-427">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-427">Pattern</span></span>

<span data-ttu-id="25414-428">Neun Buchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="25414-429">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-429">Checksum</span></span>

<span data-ttu-id="25414-430">Nicht anwendbar</span><span class="sxs-lookup"><span data-stu-id="25414-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-431">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-431">Definition</span></span>

<span data-ttu-id="25414-432">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-433">Der reguläre Ausdruck `Regex_netherlands_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-434">Ein Schlüsselwort `Keywords_netherlands_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-435">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-435">Keywords</span></span>

<span data-ttu-id="25414-436">| |</span><span class="sxs-lookup"><span data-stu-id="25414-436"></span></span>
|<span data-ttu-id="25414-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-438">niederländische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-438">dutch passport number</span></span>  <br/> <span data-ttu-id="25414-439">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-439">passport number</span></span>  <br/> <span data-ttu-id="25414-440">niederländische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="25414-441">Nederlanden paspoort Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="25414-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="25414-442">paspoort</span></span>  <br/> <span data-ttu-id="25414-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="25414-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="25414-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="25414-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="25414-445">Polen</span><span class="sxs-lookup"><span data-stu-id="25414-445">Poland</span></span>

<span data-ttu-id="25414-446">Ausführliche Informationen finden Sie im Abschnitt "Polen-Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="25414-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="25414-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="25414-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="25414-448">Format</span><span class="sxs-lookup"><span data-stu-id="25414-448">Format</span></span>

<span data-ttu-id="25414-449">Ein Buchstabe, gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-450">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-450">Pattern</span></span>

<span data-ttu-id="25414-451">Ein Buchstabe, gefolgt von sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="25414-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="25414-452">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="25414-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="25414-453">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="25414-454">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-454">Checksum</span></span>

<span data-ttu-id="25414-455">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-456">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-456">Definition</span></span>

<span data-ttu-id="25414-457">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-458">Der reguläre Ausdruck `Regex_portugal_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-459">Ein Schlüsselwort `Keywords_portugal_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-460">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-460">Keywords</span></span>

<span data-ttu-id="25414-461">| |</span><span class="sxs-lookup"><span data-stu-id="25414-461"></span></span>
|<span data-ttu-id="25414-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-463">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-463">passport number</span></span>  <br/> <span data-ttu-id="25414-464">portugiesische Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="25414-465">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-465">passport no</span></span>  <br/> <span data-ttu-id="25414-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="25414-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="25414-467">Rumänien</span><span class="sxs-lookup"><span data-stu-id="25414-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="25414-468">Format</span><span class="sxs-lookup"><span data-stu-id="25414-468">Format</span></span>

<span data-ttu-id="25414-469">Acht oder neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-470">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-470">Pattern</span></span>

<span data-ttu-id="25414-471">Acht oder neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="25414-472">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-472">Checksum</span></span>

<span data-ttu-id="25414-473">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-474">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-474">Definition</span></span>

<span data-ttu-id="25414-475">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-476">Der reguläre Ausdruck `Regex_romania_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-477">Ein Schlüsselwort `Keywords_romania_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-478">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-478">Keywords</span></span>

<span data-ttu-id="25414-479">| |</span><span class="sxs-lookup"><span data-stu-id="25414-479"></span></span>
|<span data-ttu-id="25414-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-481">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-481">passport number</span></span>  <br/> <span data-ttu-id="25414-482">rumänische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-482">romanian passport number</span></span>  <br/> <span data-ttu-id="25414-483">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-483">passport no</span></span>  <br/> <span data-ttu-id="25414-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="25414-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="25414-485">Slowakei</span><span class="sxs-lookup"><span data-stu-id="25414-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="25414-486">Format</span><span class="sxs-lookup"><span data-stu-id="25414-486">Format</span></span>

<span data-ttu-id="25414-487">Eine Ziffer oder ein Buchstabe, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-488">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-488">Pattern</span></span>

<span data-ttu-id="25414-489">Eine Ziffer oder ein Buchstabe (ohne Groß-/Kleinschreibung), gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="25414-490">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-490">Checksum</span></span>

<span data-ttu-id="25414-491">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-492">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-492">Definition</span></span>

<span data-ttu-id="25414-493">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-494">Der reguläre Ausdruck `Regex_slovakia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-495">Ein Schlüsselwort `Keywords_slovakia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-496">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-496">Keywords</span></span>

<span data-ttu-id="25414-497">| |</span><span class="sxs-lookup"><span data-stu-id="25414-497"></span></span>
|<span data-ttu-id="25414-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-499">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-499">passport number</span></span>  <br/> <span data-ttu-id="25414-500">Slowakische Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="25414-501">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-501">passport no</span></span>  <br/> <span data-ttu-id="25414-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="25414-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="25414-503">Slowenien</span><span class="sxs-lookup"><span data-stu-id="25414-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="25414-504">Format</span><span class="sxs-lookup"><span data-stu-id="25414-504">Format</span></span>

<span data-ttu-id="25414-505">Zwei Buchstaben, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-506">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-506">Pattern</span></span>

<span data-ttu-id="25414-507">Zwei Buchstaben, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="25414-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="25414-508">Der Buchstabe "P"</span><span class="sxs-lookup"><span data-stu-id="25414-508">The letter "P"</span></span>
    
- <span data-ttu-id="25414-509">Ein Großbuchstabe</span><span class="sxs-lookup"><span data-stu-id="25414-509">One uppercase letter</span></span>
    
- <span data-ttu-id="25414-510">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="25414-511">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-511">Checksum</span></span>

<span data-ttu-id="25414-512">Nein</span><span class="sxs-lookup"><span data-stu-id="25414-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-513">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-513">Definition</span></span>

<span data-ttu-id="25414-514">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-515">Der reguläre Ausdruck `Regex_slovenia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-516">Ein Schlüsselwort `Keywords_slovenia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-517">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-517">Keywords</span></span>

<span data-ttu-id="25414-518">| |</span><span class="sxs-lookup"><span data-stu-id="25414-518"></span></span>
|<span data-ttu-id="25414-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-520">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-520">passport number</span></span>  <br/> <span data-ttu-id="25414-521">slowenische Passnummer</span><span class="sxs-lookup"><span data-stu-id="25414-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="25414-522">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-522">passport no</span></span>  <br/> <span data-ttu-id="25414-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="25414-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="25414-524">Spanien</span><span class="sxs-lookup"><span data-stu-id="25414-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="25414-525">Format</span><span class="sxs-lookup"><span data-stu-id="25414-525">Format</span></span>

<span data-ttu-id="25414-526">Eine Kombination aus Buchstaben und Zahlen mit acht oder neun Zeichen ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="25414-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="25414-527">Muster</span><span class="sxs-lookup"><span data-stu-id="25414-527">Pattern</span></span>

<span data-ttu-id="25414-528">Eine Kombination aus Buchstaben und Zahlen aus acht oder neun Zeichen:</span><span class="sxs-lookup"><span data-stu-id="25414-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="25414-529">Zwei Ziffern oder Buchstaben</span><span class="sxs-lookup"><span data-stu-id="25414-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="25414-530">Eine Ziffer oder ein Buchstabe (optional)</span><span class="sxs-lookup"><span data-stu-id="25414-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="25414-531">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="25414-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="25414-532">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="25414-532">Checksum</span></span>

<span data-ttu-id="25414-533">Nicht anwendbar</span><span class="sxs-lookup"><span data-stu-id="25414-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="25414-534">Definition</span><span class="sxs-lookup"><span data-stu-id="25414-534">Definition</span></span>

<span data-ttu-id="25414-535">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25414-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="25414-536">Der reguläre Ausdruck `Regex_spain_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="25414-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="25414-537">Ein Schlüsselwort `Keywords_spain_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="25414-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="25414-538">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25414-538">Keywords</span></span>

<span data-ttu-id="25414-539">| |</span><span class="sxs-lookup"><span data-stu-id="25414-539"></span></span>
|<span data-ttu-id="25414-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="25414-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="25414-541">Pass</span><span class="sxs-lookup"><span data-stu-id="25414-541">passport</span></span>  <br/> <span data-ttu-id="25414-542">Spanien-Passport</span><span class="sxs-lookup"><span data-stu-id="25414-542">spain passport</span></span>  <br/> <span data-ttu-id="25414-543">Passport-Buch</span><span class="sxs-lookup"><span data-stu-id="25414-543">passport book</span></span>  <br/> <span data-ttu-id="25414-544">passport number</span><span class="sxs-lookup"><span data-stu-id="25414-544">passport number</span></span>  <br/> <span data-ttu-id="25414-545">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="25414-545">passport no</span></span>  <br/> <span data-ttu-id="25414-546">Libreta Pasaporte</span><span class="sxs-lookup"><span data-stu-id="25414-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="25414-547">número Pasaporte</span><span class="sxs-lookup"><span data-stu-id="25414-547">número pasaporte</span></span>  <br/> <span data-ttu-id="25414-548">ESPAÑA PASAPORTE</span><span class="sxs-lookup"><span data-stu-id="25414-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="25414-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="25414-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="25414-550">Schweden</span><span class="sxs-lookup"><span data-stu-id="25414-550">Sweden</span></span>

<span data-ttu-id="25414-551">Ausführliche Informationen finden Sie im Abschnitt "schwedische Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="25414-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="25414-552">UK</span><span class="sxs-lookup"><span data-stu-id="25414-552">UK</span></span>

<span data-ttu-id="25414-553">Ausführliche Informationen finden Sie im Abschnitt "U.S./U.K.</span><span class="sxs-lookup"><span data-stu-id="25414-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="25414-554">Passport-Nummer "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="25414-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="25414-555">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25414-555">See also</span></span>

[<span data-ttu-id="25414-556">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="25414-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

