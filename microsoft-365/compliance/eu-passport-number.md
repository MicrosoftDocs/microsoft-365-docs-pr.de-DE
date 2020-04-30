---
title: EU-Passport-Nummer
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
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp EU-Passport-Nummern erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: 56eb79dd067ca89600f92ea57eaaf01e562f9388
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938739"
---
# <a name="eu-passport-number"></a><span data-ttu-id="33bbe-104">EU-Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-104">EU Passport Number</span></span>

<span data-ttu-id="33bbe-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp EU-Passport-Nummern erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="33bbe-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="33bbe-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="33bbe-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="33bbe-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="33bbe-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-108">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-108">Format</span></span>

<span data-ttu-id="33bbe-109">Ein Buchstabe, gefolgt von einem optionalen Leerzeichen und sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-110">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-110">Pattern</span></span>

<span data-ttu-id="33bbe-111">Eine Kombination aus einem Buchstaben, sieben Ziffern und einem Leerzeichen:</span><span class="sxs-lookup"><span data-stu-id="33bbe-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="33bbe-112">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="33bbe-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="33bbe-113">Ein Leerzeichen (optional)</span><span class="sxs-lookup"><span data-stu-id="33bbe-113">One space (optional)</span></span>
    
- <span data-ttu-id="33bbe-114">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33bbe-115">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-115">Checksum</span></span>

<span data-ttu-id="33bbe-116">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="33bbe-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-117">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-117">Definition</span></span>

<span data-ttu-id="33bbe-118">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-119">Der reguläre Ausdruck `Regex_austria_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-120">Ein Schlüsselwort `Keywords_austria_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-121">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-121">Keywords</span></span>

<span data-ttu-id="33bbe-122">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-122">| |</span></span>
|<span data-ttu-id="33bbe-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-124">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-124">passport number</span></span>  <br/> <span data-ttu-id="33bbe-125">Österreichische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-125">austrian passport number</span></span>  <br/> <span data-ttu-id="33bbe-126">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-126">passport no</span></span>  <br/> <span data-ttu-id="33bbe-127">Reisepass</span><span class="sxs-lookup"><span data-stu-id="33bbe-127">reisepass</span></span>  <br/> <span data-ttu-id="33bbe-128">österreichisch Reisepass</span><span class="sxs-lookup"><span data-stu-id="33bbe-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="33bbe-129">Belgien</span><span class="sxs-lookup"><span data-stu-id="33bbe-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-130">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-130">Format</span></span>

<span data-ttu-id="33bbe-131">Zwei Buchstaben, gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-132">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-132">Pattern</span></span>

<span data-ttu-id="33bbe-133">Zwei Buchstaben und gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33bbe-134">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-134">Checksum</span></span>

<span data-ttu-id="33bbe-135">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="33bbe-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-136">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-136">Definition</span></span>

<span data-ttu-id="33bbe-137">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-138">Der reguläre Ausdruck `Regex_belgium_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-139">Ein Schlüsselwort `Keywords_belgium_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-140">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-140">Keywords</span></span>

<span data-ttu-id="33bbe-141">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-141">| |</span></span>
|<span data-ttu-id="33bbe-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-143">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-143">passport number</span></span>  <br/> <span data-ttu-id="33bbe-144">belgische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-144">belgian passport number</span></span>  <br/> <span data-ttu-id="33bbe-145">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-145">passport no</span></span>  <br/> <span data-ttu-id="33bbe-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="33bbe-146">paspoort</span></span>  <br/> <span data-ttu-id="33bbe-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="33bbe-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="33bbe-148">reisepass kein</span></span>  <br/> <span data-ttu-id="33bbe-149">Reisepass</span><span class="sxs-lookup"><span data-stu-id="33bbe-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="33bbe-150">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="33bbe-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-151">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-151">Format</span></span>

<span data-ttu-id="33bbe-152">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-153">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-153">Pattern</span></span>

 <span data-ttu-id="33bbe-154">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="33bbe-155">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-155">Checksum</span></span>

<span data-ttu-id="33bbe-156">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-157">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-157">Definition</span></span>

<span data-ttu-id="33bbe-158">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-159">Der reguläre Ausdruck `Regex_bulgaria_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-160">Ein Schlüsselwort `Keywords_bulgaria_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-161">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-161">Keywords</span></span>

<span data-ttu-id="33bbe-162">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-162">| |</span></span>
|<span data-ttu-id="33bbe-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-164">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-164">passport number</span></span>  <br/> <span data-ttu-id="33bbe-165">Bulgarische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="33bbe-166">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-166">passport no</span></span>  <br/> <span data-ttu-id="33bbe-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="33bbe-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="33bbe-168">Kroatien</span><span class="sxs-lookup"><span data-stu-id="33bbe-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-169">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-169">Format</span></span>

<span data-ttu-id="33bbe-170">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-171">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-171">Pattern</span></span>

 <span data-ttu-id="33bbe-172">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="33bbe-173">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-173">Checksum</span></span>

<span data-ttu-id="33bbe-174">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-175">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-175">Definition</span></span>

<span data-ttu-id="33bbe-176">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-177">Der reguläre Ausdruck `Regex_croatia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-178">Ein Schlüsselwort `Keywords_croatia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-179">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-179">Keywords</span></span>

<span data-ttu-id="33bbe-180">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-180">| |</span></span>
|<span data-ttu-id="33bbe-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-182">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-182">passport number</span></span>  <br/> <span data-ttu-id="33bbe-183">Kroatische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-183">croatian passport number</span></span>  <br/> <span data-ttu-id="33bbe-184">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-184">passport no</span></span>  <br/> <span data-ttu-id="33bbe-185">Broj putovnice</span><span class="sxs-lookup"><span data-stu-id="33bbe-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="33bbe-186">Zypern</span><span class="sxs-lookup"><span data-stu-id="33bbe-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-187">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-187">Format</span></span>

<span data-ttu-id="33bbe-188">Ein Buchstabe, gefolgt von 6-8 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-189">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-189">Pattern</span></span>

<span data-ttu-id="33bbe-190">Ein Buchstabe, gefolgt von sechs bis acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33bbe-191">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-191">Checksum</span></span>

<span data-ttu-id="33bbe-192">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-193">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-193">Definition</span></span>

<span data-ttu-id="33bbe-194">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-195">Der reguläre Ausdruck `Regex_cyprus_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-196">Ein Schlüsselwort `Keywords_cyprus_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-197">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-197">Keywords</span></span>

<span data-ttu-id="33bbe-198">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-198">| |</span></span>
|<span data-ttu-id="33bbe-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-200">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-200">passport number</span></span>  <br/> <span data-ttu-id="33bbe-201">Zypern-Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="33bbe-202">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-202">passport no</span></span>  <br/> <span data-ttu-id="33bbe-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="33bbe-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="33bbe-204">Tschechien</span><span class="sxs-lookup"><span data-stu-id="33bbe-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-205">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-205">Format</span></span>

<span data-ttu-id="33bbe-206">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-207">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-207">Pattern</span></span>

<span data-ttu-id="33bbe-208">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33bbe-209">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-209">Checksum</span></span>

<span data-ttu-id="33bbe-210">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-211">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-211">Definition</span></span>

<span data-ttu-id="33bbe-212">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-213">Der reguläre Ausdruck `Regex_czech_republic_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-214">Ein Schlüsselwort `Keywords_czech_republic_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-215">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-215">Keywords</span></span>

<span data-ttu-id="33bbe-216">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-216">| |</span></span>
|<span data-ttu-id="33bbe-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-218">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-218">passport number</span></span>  <br/> <span data-ttu-id="33bbe-219">Tschechische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-219">czech passport number</span></span>  <br/> <span data-ttu-id="33bbe-220">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-220">passport no</span></span>  <br/> <span data-ttu-id="33bbe-221">Cestovní Pas</span><span class="sxs-lookup"><span data-stu-id="33bbe-221">cestovní pas</span></span>  <br/> <span data-ttu-id="33bbe-222">Pas</span><span class="sxs-lookup"><span data-stu-id="33bbe-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="33bbe-223">Dänemark</span><span class="sxs-lookup"><span data-stu-id="33bbe-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-224">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-224">Format</span></span>

<span data-ttu-id="33bbe-225">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-226">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-226">Pattern</span></span>

 <span data-ttu-id="33bbe-227">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="33bbe-228">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-228">Checksum</span></span>

<span data-ttu-id="33bbe-229">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-230">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-230">Definition</span></span>

<span data-ttu-id="33bbe-231">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-232">Der reguläre Ausdruck `Regex_denmark_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-233">Ein Schlüsselwort `Keywords_denmark_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-234">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-234">Keywords</span></span>

<span data-ttu-id="33bbe-235">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-235">| |</span></span>
|<span data-ttu-id="33bbe-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-237">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-237">passport number</span></span>  <br/> <span data-ttu-id="33bbe-238">dänische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-238">danish passport number</span></span>  <br/> <span data-ttu-id="33bbe-239">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-239">passport no</span></span>  <br/> <span data-ttu-id="33bbe-240">Pas</span><span class="sxs-lookup"><span data-stu-id="33bbe-240">pas</span></span>  <br/> <span data-ttu-id="33bbe-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="33bbe-242">Estland</span><span class="sxs-lookup"><span data-stu-id="33bbe-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-243">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-243">Format</span></span>

<span data-ttu-id="33bbe-244">Ein Buchstabe, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-245">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-245">Pattern</span></span>

<span data-ttu-id="33bbe-246">Ein Buchstabe, gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33bbe-247">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-247">Checksum</span></span>

<span data-ttu-id="33bbe-248">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-249">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-249">Definition</span></span>

<span data-ttu-id="33bbe-250">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-251">Der reguläre Ausdruck `Regex_estonia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-252">Ein Schlüsselwort `Keywords_estonia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-253">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-253">Keywords</span></span>

<span data-ttu-id="33bbe-254">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-254">| |</span></span>
|<span data-ttu-id="33bbe-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-256">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-256">passport number</span></span>  <br/> <span data-ttu-id="33bbe-257">Estnische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-257">estonian passport number</span></span>  <br/> <span data-ttu-id="33bbe-258">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-258">passport no</span></span>  <br/> <span data-ttu-id="33bbe-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="33bbe-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="33bbe-260">Finnland</span><span class="sxs-lookup"><span data-stu-id="33bbe-260">Finland</span></span>

<span data-ttu-id="33bbe-261">Ausführliche Informationen finden Sie im Abschnitt "Finnland-Passport-Nummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="33bbe-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="33bbe-262">Frankreich</span><span class="sxs-lookup"><span data-stu-id="33bbe-262">France</span></span>

<span data-ttu-id="33bbe-263">Ausführliche Informationen finden Sie im Abschnitt "französische Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="33bbe-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="33bbe-264">Deutschland</span><span class="sxs-lookup"><span data-stu-id="33bbe-264">Germany</span></span>

<span data-ttu-id="33bbe-265">Ausführliche Informationen finden Sie im Abschnitt "Deutsche Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="33bbe-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="33bbe-266">Griechenland</span><span class="sxs-lookup"><span data-stu-id="33bbe-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-267">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-267">Format</span></span>

<span data-ttu-id="33bbe-268">Zwei Buchstaben, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-269">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-269">Pattern</span></span>

<span data-ttu-id="33bbe-270">Zwei Buchstaben gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33bbe-271">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-271">Checksum</span></span>

<span data-ttu-id="33bbe-272">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-273">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-273">Definition</span></span>

<span data-ttu-id="33bbe-274">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-275">Der reguläre Ausdruck `Regex_greece_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-276">Ein Schlüsselwort `Keywords_greece_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-277">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-277">Keywords</span></span>

<span data-ttu-id="33bbe-278">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-278">| |</span></span>
|<span data-ttu-id="33bbe-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-280">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-280">passport number</span></span>  <br/> <span data-ttu-id="33bbe-281">griechische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-281">greek passport number</span></span>  <br/> <span data-ttu-id="33bbe-282">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-282">passport no</span></span>  <br/> <span data-ttu-id="33bbe-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="33bbe-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="33bbe-284">Ungarn</span><span class="sxs-lookup"><span data-stu-id="33bbe-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-285">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-285">Format</span></span>

<span data-ttu-id="33bbe-286">Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-287">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-287">Pattern</span></span>

<span data-ttu-id="33bbe-288">Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33bbe-289">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-289">Checksum</span></span>

<span data-ttu-id="33bbe-290">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-291">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-291">Definition</span></span>

<span data-ttu-id="33bbe-292">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-293">Der reguläre Ausdruck `Regex_hungary_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-294">Ein Schlüsselwort `Keywords_hungary_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-295">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-295">Keywords</span></span>

<span data-ttu-id="33bbe-296">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-296">| |</span></span>
|<span data-ttu-id="33bbe-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-298">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-298">passport number</span></span>  <br/> <span data-ttu-id="33bbe-299">ungarische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="33bbe-300">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-300">passport no</span></span>  <br/> <span data-ttu-id="33bbe-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="33bbe-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="33bbe-302">Irland</span><span class="sxs-lookup"><span data-stu-id="33bbe-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-303">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-303">Format</span></span>

<span data-ttu-id="33bbe-304">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-305">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-305">Pattern</span></span>

<span data-ttu-id="33bbe-306">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="33bbe-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="33bbe-307">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="33bbe-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="33bbe-308">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33bbe-309">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-309">Checksum</span></span>

<span data-ttu-id="33bbe-310">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-311">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-311">Definition</span></span>

<span data-ttu-id="33bbe-312">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-313">Der reguläre Ausdruck `Regex_ireland_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-314">Ein Schlüsselwort `Keywords_ireland_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-315">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-315">Keywords</span></span>

<span data-ttu-id="33bbe-316">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-316">| |</span></span>
|<span data-ttu-id="33bbe-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-318">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-318">passport number</span></span>  <br/> <span data-ttu-id="33bbe-319">irische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-319">irish passport number</span></span>  <br/> <span data-ttu-id="33bbe-320">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-320">passport no</span></span>  <br/> <span data-ttu-id="33bbe-321">Pas</span><span class="sxs-lookup"><span data-stu-id="33bbe-321">pas</span></span>  <br/> <span data-ttu-id="33bbe-322">Pass</span><span class="sxs-lookup"><span data-stu-id="33bbe-322">passport</span></span>  <br/> <span data-ttu-id="33bbe-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="33bbe-323">passeport</span></span>  <br/> <span data-ttu-id="33bbe-324">Passeport numero</span><span class="sxs-lookup"><span data-stu-id="33bbe-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="33bbe-325">Italien</span><span class="sxs-lookup"><span data-stu-id="33bbe-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-326">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-326">Format</span></span>

<span data-ttu-id="33bbe-327">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-328">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-328">Pattern</span></span>

<span data-ttu-id="33bbe-329">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="33bbe-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="33bbe-330">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="33bbe-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="33bbe-331">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33bbe-332">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-332">Checksum</span></span>

<span data-ttu-id="33bbe-333">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="33bbe-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-334">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-334">Definition</span></span>

<span data-ttu-id="33bbe-335">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-336">Der reguläre Ausdruck `Regex_italy_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-337">Ein Schlüsselwort `Keywords_italy_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-338">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-338">Keywords</span></span>

<span data-ttu-id="33bbe-339">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-339">| |</span></span>
|<span data-ttu-id="33bbe-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-341">italienische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-341">italian passport number</span></span>  <br/> <span data-ttu-id="33bbe-342">Repubblica Italiana Passa Porto</span><span class="sxs-lookup"><span data-stu-id="33bbe-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="33bbe-343">Passa Porto</span><span class="sxs-lookup"><span data-stu-id="33bbe-343">passaporto</span></span>  <br/> <span data-ttu-id="33bbe-344">Passa Porto Italiana</span><span class="sxs-lookup"><span data-stu-id="33bbe-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="33bbe-345">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-345">passport number</span></span>  <br/> <span data-ttu-id="33bbe-346">Italiana Passa Porto numero</span><span class="sxs-lookup"><span data-stu-id="33bbe-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="33bbe-347">Passa Porto numero</span><span class="sxs-lookup"><span data-stu-id="33bbe-347">passaporto numero</span></span>  <br/> <span data-ttu-id="33bbe-348">Numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="33bbe-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="33bbe-349">Numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="33bbe-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="33bbe-350">Lettland</span><span class="sxs-lookup"><span data-stu-id="33bbe-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-351">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-351">Format</span></span>

<span data-ttu-id="33bbe-352">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-353">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-353">Pattern</span></span>

<span data-ttu-id="33bbe-354">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="33bbe-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="33bbe-355">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="33bbe-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="33bbe-356">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33bbe-357">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-357">Checksum</span></span>

<span data-ttu-id="33bbe-358">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-359">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-359">Definition</span></span>

<span data-ttu-id="33bbe-360">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-361">Der reguläre Ausdruck `Regex_latvia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-362">Ein Schlüsselwort `Keywords_latvia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-363">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-363">Keywords</span></span>

<span data-ttu-id="33bbe-364">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-364">| |</span></span>
|<span data-ttu-id="33bbe-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-366">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-366">passport number</span></span>  <br/> <span data-ttu-id="33bbe-367">Lettische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-367">latvian passport number</span></span>  <br/> <span data-ttu-id="33bbe-368">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-368">passport no</span></span>  <br/> <span data-ttu-id="33bbe-369">Pase numurs</span><span class="sxs-lookup"><span data-stu-id="33bbe-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="33bbe-370">Litauen</span><span class="sxs-lookup"><span data-stu-id="33bbe-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-371">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-371">Format</span></span>

<span data-ttu-id="33bbe-372">Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-373">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-373">Pattern</span></span>

<span data-ttu-id="33bbe-374">Acht Ziffern oder Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="33bbe-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33bbe-375">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-375">Checksum</span></span>

<span data-ttu-id="33bbe-376">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="33bbe-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-377">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-377">Definition</span></span>

<span data-ttu-id="33bbe-378">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-379">Der reguläre Ausdruck `Regex_lithuania_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-380">Ein Schlüsselwort `Keywords_lithuania_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-381">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-381">Keywords</span></span>

<span data-ttu-id="33bbe-382">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-382">| |</span></span>
|<span data-ttu-id="33bbe-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-384">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-384">passport number</span></span>  <br/> <span data-ttu-id="33bbe-385">lithunian Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="33bbe-386">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-386">passport no</span></span>  <br/> <span data-ttu-id="33bbe-387">Paso Numeris</span><span class="sxs-lookup"><span data-stu-id="33bbe-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="33bbe-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="33bbe-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-389">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-389">Format</span></span>

<span data-ttu-id="33bbe-390">Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-391">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-391">Pattern</span></span>

<span data-ttu-id="33bbe-392">Acht Ziffern oder Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="33bbe-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33bbe-393">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-393">Checksum</span></span>

<span data-ttu-id="33bbe-394">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-395">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-395">Definition</span></span>

<span data-ttu-id="33bbe-396">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-397">Der reguläre Ausdruck `Regex_nation_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-398">Ein Schlüsselwort `Keywords_nation_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-399">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-399">Keywords</span></span>

<span data-ttu-id="33bbe-400">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-400">| |</span></span>
|<span data-ttu-id="33bbe-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-402">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-402">passport number</span></span>  <br/> <span data-ttu-id="33bbe-403">Lettische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-403">latvian passport number</span></span>  <br/> <span data-ttu-id="33bbe-404">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-404">passport no</span></span>  <br/> <span data-ttu-id="33bbe-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="33bbe-406">Malta</span><span class="sxs-lookup"><span data-stu-id="33bbe-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-407">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-407">Format</span></span>

<span data-ttu-id="33bbe-408">Sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-409">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-409">Pattern</span></span>

 <span data-ttu-id="33bbe-410">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="33bbe-411">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-411">Checksum</span></span>

<span data-ttu-id="33bbe-412">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-413">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-413">Definition</span></span>

<span data-ttu-id="33bbe-414">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-415">Der reguläre Ausdruck `Regex_malta_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-416">Ein Schlüsselwort `Keywords_malta_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-417">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-417">Keywords</span></span>

<span data-ttu-id="33bbe-418">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-418">| |</span></span>
|<span data-ttu-id="33bbe-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-420">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-420">passport number</span></span>  <br/> <span data-ttu-id="33bbe-421">Maltesische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-421">maltese passport number</span></span>  <br/> <span data-ttu-id="33bbe-422">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-422">passport no</span></span>  <br/> <span data-ttu-id="33bbe-423">numru Tal-Passaport</span><span class="sxs-lookup"><span data-stu-id="33bbe-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="33bbe-424">Niederlande</span><span class="sxs-lookup"><span data-stu-id="33bbe-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-425">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-425">Format</span></span>

<span data-ttu-id="33bbe-426">Neun Buchstaben oder Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-427">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-427">Pattern</span></span>

<span data-ttu-id="33bbe-428">Neun Buchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33bbe-429">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-429">Checksum</span></span>

<span data-ttu-id="33bbe-430">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="33bbe-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-431">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-431">Definition</span></span>

<span data-ttu-id="33bbe-432">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-433">Der reguläre Ausdruck `Regex_netherlands_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-434">Ein Schlüsselwort `Keywords_netherlands_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-435">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-435">Keywords</span></span>

<span data-ttu-id="33bbe-436">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-436">| |</span></span>
|<span data-ttu-id="33bbe-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-438">niederländische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-438">dutch passport number</span></span>  <br/> <span data-ttu-id="33bbe-439">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-439">passport number</span></span>  <br/> <span data-ttu-id="33bbe-440">niederländische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="33bbe-441">Nederlanden paspoort Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="33bbe-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="33bbe-442">paspoort</span></span>  <br/> <span data-ttu-id="33bbe-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="33bbe-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="33bbe-445">Polen</span><span class="sxs-lookup"><span data-stu-id="33bbe-445">Poland</span></span>

<span data-ttu-id="33bbe-446">Ausführliche Informationen finden Sie im Abschnitt "Polen-Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="33bbe-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="33bbe-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="33bbe-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-448">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-448">Format</span></span>

<span data-ttu-id="33bbe-449">Ein Buchstabe, gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-450">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-450">Pattern</span></span>

<span data-ttu-id="33bbe-451">Ein Buchstabe, gefolgt von sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="33bbe-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="33bbe-452">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="33bbe-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="33bbe-453">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33bbe-454">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-454">Checksum</span></span>

<span data-ttu-id="33bbe-455">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-456">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-456">Definition</span></span>

<span data-ttu-id="33bbe-457">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-458">Der reguläre Ausdruck `Regex_portugal_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-459">Ein Schlüsselwort `Keywords_portugal_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-460">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-460">Keywords</span></span>

<span data-ttu-id="33bbe-461">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-461">| |</span></span>
|<span data-ttu-id="33bbe-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-463">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-463">passport number</span></span>  <br/> <span data-ttu-id="33bbe-464">portugiesische Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="33bbe-465">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-465">passport no</span></span>  <br/> <span data-ttu-id="33bbe-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="33bbe-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="33bbe-467">Rumänien</span><span class="sxs-lookup"><span data-stu-id="33bbe-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-468">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-468">Format</span></span>

<span data-ttu-id="33bbe-469">Acht oder neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-470">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-470">Pattern</span></span>

<span data-ttu-id="33bbe-471">Acht oder neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33bbe-472">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-472">Checksum</span></span>

<span data-ttu-id="33bbe-473">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-474">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-474">Definition</span></span>

<span data-ttu-id="33bbe-475">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-476">Der reguläre Ausdruck `Regex_romania_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-477">Ein Schlüsselwort `Keywords_romania_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-478">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-478">Keywords</span></span>

<span data-ttu-id="33bbe-479">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-479">| |</span></span>
|<span data-ttu-id="33bbe-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-481">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-481">passport number</span></span>  <br/> <span data-ttu-id="33bbe-482">rumänische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-482">romanian passport number</span></span>  <br/> <span data-ttu-id="33bbe-483">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-483">passport no</span></span>  <br/> <span data-ttu-id="33bbe-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="33bbe-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="33bbe-485">Slowakei</span><span class="sxs-lookup"><span data-stu-id="33bbe-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-486">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-486">Format</span></span>

<span data-ttu-id="33bbe-487">Eine Ziffer oder ein Buchstabe, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-488">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-488">Pattern</span></span>

<span data-ttu-id="33bbe-489">Eine Ziffer oder ein Buchstabe (ohne Groß-/Kleinschreibung), gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33bbe-490">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-490">Checksum</span></span>

<span data-ttu-id="33bbe-491">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-492">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-492">Definition</span></span>

<span data-ttu-id="33bbe-493">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-494">Der reguläre Ausdruck `Regex_slovakia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-495">Ein Schlüsselwort `Keywords_slovakia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-496">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-496">Keywords</span></span>

<span data-ttu-id="33bbe-497">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-497">| |</span></span>
|<span data-ttu-id="33bbe-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-499">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-499">passport number</span></span>  <br/> <span data-ttu-id="33bbe-500">Slowakische Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="33bbe-501">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-501">passport no</span></span>  <br/> <span data-ttu-id="33bbe-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="33bbe-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="33bbe-503">Slowenien</span><span class="sxs-lookup"><span data-stu-id="33bbe-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-504">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-504">Format</span></span>

<span data-ttu-id="33bbe-505">Zwei Buchstaben, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-506">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-506">Pattern</span></span>

<span data-ttu-id="33bbe-507">Zwei Buchstaben, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="33bbe-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="33bbe-508">Der Buchstabe "P"</span><span class="sxs-lookup"><span data-stu-id="33bbe-508">The letter "P"</span></span>
    
- <span data-ttu-id="33bbe-509">Ein Großbuchstabe</span><span class="sxs-lookup"><span data-stu-id="33bbe-509">One uppercase letter</span></span>
    
- <span data-ttu-id="33bbe-510">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33bbe-511">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-511">Checksum</span></span>

<span data-ttu-id="33bbe-512">Nein</span><span class="sxs-lookup"><span data-stu-id="33bbe-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-513">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-513">Definition</span></span>

<span data-ttu-id="33bbe-514">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-515">Der reguläre Ausdruck `Regex_slovenia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-516">Ein Schlüsselwort `Keywords_slovenia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-517">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-517">Keywords</span></span>

<span data-ttu-id="33bbe-518">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-518">| |</span></span>
|<span data-ttu-id="33bbe-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-520">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-520">passport number</span></span>  <br/> <span data-ttu-id="33bbe-521">slowenische Passnummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="33bbe-522">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-522">passport no</span></span>  <br/> <span data-ttu-id="33bbe-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="33bbe-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="33bbe-524">Spanien</span><span class="sxs-lookup"><span data-stu-id="33bbe-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="33bbe-525">Format</span><span class="sxs-lookup"><span data-stu-id="33bbe-525">Format</span></span>

<span data-ttu-id="33bbe-526">Eine Kombination aus Buchstaben und Zahlen mit acht oder neun Zeichen ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33bbe-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33bbe-527">Muster</span><span class="sxs-lookup"><span data-stu-id="33bbe-527">Pattern</span></span>

<span data-ttu-id="33bbe-528">Eine Kombination aus Buchstaben und Zahlen aus acht oder neun Zeichen:</span><span class="sxs-lookup"><span data-stu-id="33bbe-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="33bbe-529">Zwei Ziffern oder Buchstaben</span><span class="sxs-lookup"><span data-stu-id="33bbe-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="33bbe-530">Eine Ziffer oder ein Buchstabe (optional)</span><span class="sxs-lookup"><span data-stu-id="33bbe-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="33bbe-531">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="33bbe-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33bbe-532">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="33bbe-532">Checksum</span></span>

<span data-ttu-id="33bbe-533">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="33bbe-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="33bbe-534">Definition</span><span class="sxs-lookup"><span data-stu-id="33bbe-534">Definition</span></span>

<span data-ttu-id="33bbe-535">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33bbe-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33bbe-536">Der reguläre Ausdruck `Regex_spain_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="33bbe-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33bbe-537">Ein Schlüsselwort `Keywords_spain_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="33bbe-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33bbe-538">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33bbe-538">Keywords</span></span>

<span data-ttu-id="33bbe-539">| |</span><span class="sxs-lookup"><span data-stu-id="33bbe-539">| |</span></span>
|<span data-ttu-id="33bbe-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="33bbe-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="33bbe-541">Pass</span><span class="sxs-lookup"><span data-stu-id="33bbe-541">passport</span></span>  <br/> <span data-ttu-id="33bbe-542">Spanien-Passport</span><span class="sxs-lookup"><span data-stu-id="33bbe-542">spain passport</span></span>  <br/> <span data-ttu-id="33bbe-543">Passport-Buch</span><span class="sxs-lookup"><span data-stu-id="33bbe-543">passport book</span></span>  <br/> <span data-ttu-id="33bbe-544">passport number</span><span class="sxs-lookup"><span data-stu-id="33bbe-544">passport number</span></span>  <br/> <span data-ttu-id="33bbe-545">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="33bbe-545">passport no</span></span>  <br/> <span data-ttu-id="33bbe-546">Libreta Pasaporte</span><span class="sxs-lookup"><span data-stu-id="33bbe-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="33bbe-547">número Pasaporte</span><span class="sxs-lookup"><span data-stu-id="33bbe-547">número pasaporte</span></span>  <br/> <span data-ttu-id="33bbe-548">ESPAÑA PASAPORTE</span><span class="sxs-lookup"><span data-stu-id="33bbe-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="33bbe-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="33bbe-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="33bbe-550">Schweden</span><span class="sxs-lookup"><span data-stu-id="33bbe-550">Sweden</span></span>

<span data-ttu-id="33bbe-551">Ausführliche Informationen finden Sie im Abschnitt "schwedische Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="33bbe-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="33bbe-552">UK</span><span class="sxs-lookup"><span data-stu-id="33bbe-552">UK</span></span>

<span data-ttu-id="33bbe-553">Ausführliche Informationen finden Sie im Abschnitt "U.S./U.K.</span><span class="sxs-lookup"><span data-stu-id="33bbe-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="33bbe-554">Passport-Nummer "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="33bbe-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="33bbe-555">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33bbe-555">See also</span></span>

[<span data-ttu-id="33bbe-556">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="33bbe-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

