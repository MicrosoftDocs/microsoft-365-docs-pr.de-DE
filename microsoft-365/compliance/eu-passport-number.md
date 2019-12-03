---
title: EU-Passport-Nummer
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp EU-Passport-Nummern erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: 44ee6e7b46d79772bcd3aec0fd26265f58f6c4c6
ms.sourcegitcommit: 3fd6d175c1954ce463198e835d1d8f2f91d80d79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2019
ms.locfileid: "39662800"
---
# <a name="eu-passport-number"></a><span data-ttu-id="f0c0f-104">EU-Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-104">EU Passport Number</span></span>

<span data-ttu-id="f0c0f-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp EU-Passport-Nummern erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="f0c0f-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="f0c0f-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="f0c0f-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-108">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-108">Format</span></span>

<span data-ttu-id="f0c0f-109">Ein Buchstabe, gefolgt von einem optionalen Leerzeichen und sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-110">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-110">Pattern</span></span>

<span data-ttu-id="f0c0f-111">Eine Kombination aus einem Buchstaben, sieben Ziffern und einem Leerzeichen:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="f0c0f-112">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="f0c0f-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="f0c0f-113">Ein Leerzeichen (optional)</span><span class="sxs-lookup"><span data-stu-id="f0c0f-113">One space (optional)</span></span>
    
- <span data-ttu-id="f0c0f-114">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0c0f-115">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-115">Checksum</span></span>

<span data-ttu-id="f0c0f-116">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="f0c0f-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-117">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-117">Definition</span></span>

<span data-ttu-id="f0c0f-118">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-119">Der reguläre Ausdruck `Regex_austria_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-120">Ein Schlüsselwort `Keywords_austria_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-121">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-121">Keywords</span></span>

<span data-ttu-id="f0c0f-122">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-122"></span></span>
|<span data-ttu-id="f0c0f-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-124">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-124">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-125">Österreichische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-125">austrian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-126">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-126">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-127">Reisepass</span><span class="sxs-lookup"><span data-stu-id="f0c0f-127">reisepass</span></span>  <br/> <span data-ttu-id="f0c0f-128">österreichisch Reisepass</span><span class="sxs-lookup"><span data-stu-id="f0c0f-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="f0c0f-129">Belgien</span><span class="sxs-lookup"><span data-stu-id="f0c0f-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-130">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-130">Format</span></span>

<span data-ttu-id="f0c0f-131">Zwei Buchstaben, gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-132">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-132">Pattern</span></span>

<span data-ttu-id="f0c0f-133">Zwei Buchstaben und gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-134">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-134">Checksum</span></span>

<span data-ttu-id="f0c0f-135">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="f0c0f-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-136">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-136">Definition</span></span>

<span data-ttu-id="f0c0f-137">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-138">Der reguläre Ausdruck `Regex_belgium_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-139">Ein Schlüsselwort `Keywords_belgium_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-140">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-140">Keywords</span></span>

<span data-ttu-id="f0c0f-141">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-141"></span></span>
|<span data-ttu-id="f0c0f-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-143">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-143">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-144">belgische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-144">belgian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-145">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-145">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="f0c0f-146">paspoort</span></span>  <br/> <span data-ttu-id="f0c0f-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="f0c0f-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-148">reisepass kein</span></span>  <br/> <span data-ttu-id="f0c0f-149">Reisepass</span><span class="sxs-lookup"><span data-stu-id="f0c0f-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="f0c0f-150">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="f0c0f-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-151">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-151">Format</span></span>

<span data-ttu-id="f0c0f-152">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-153">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-153">Pattern</span></span>

 <span data-ttu-id="f0c0f-154">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-155">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-155">Checksum</span></span>

<span data-ttu-id="f0c0f-156">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-157">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-157">Definition</span></span>

<span data-ttu-id="f0c0f-158">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-159">Der reguläre Ausdruck `Regex_bulgaria_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-160">Ein Schlüsselwort `Keywords_bulgaria_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-161">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-161">Keywords</span></span>

<span data-ttu-id="f0c0f-162">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-162"></span></span>
|<span data-ttu-id="f0c0f-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-164">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-164">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-165">Bulgarische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-166">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-166">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="f0c0f-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="f0c0f-168">Kroatien</span><span class="sxs-lookup"><span data-stu-id="f0c0f-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-169">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-169">Format</span></span>

<span data-ttu-id="f0c0f-170">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-171">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-171">Pattern</span></span>

 <span data-ttu-id="f0c0f-172">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-173">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-173">Checksum</span></span>

<span data-ttu-id="f0c0f-174">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-175">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-175">Definition</span></span>

<span data-ttu-id="f0c0f-176">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-177">Der reguläre Ausdruck `Regex_croatia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-178">Ein Schlüsselwort `Keywords_croatia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-179">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-179">Keywords</span></span>

<span data-ttu-id="f0c0f-180">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-180"></span></span>
|<span data-ttu-id="f0c0f-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-182">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-182">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-183">Kroatische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-183">croatian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-184">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-184">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-185">Broj putovnice</span><span class="sxs-lookup"><span data-stu-id="f0c0f-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="f0c0f-186">Zypern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-187">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-187">Format</span></span>

<span data-ttu-id="f0c0f-188">Ein Buchstabe, gefolgt von 6-8 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-189">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-189">Pattern</span></span>

<span data-ttu-id="f0c0f-190">Ein Buchstabe, gefolgt von sechs bis acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-191">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-191">Checksum</span></span>

<span data-ttu-id="f0c0f-192">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-193">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-193">Definition</span></span>

<span data-ttu-id="f0c0f-194">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-195">Der reguläre Ausdruck `Regex_cyprus_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-196">Ein Schlüsselwort `Keywords_cyprus_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-197">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-197">Keywords</span></span>

<span data-ttu-id="f0c0f-198">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-198"></span></span>
|<span data-ttu-id="f0c0f-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-200">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-200">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-201">Zypern-Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="f0c0f-202">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-202">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="f0c0f-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="f0c0f-204">Tschechien</span><span class="sxs-lookup"><span data-stu-id="f0c0f-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-205">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-205">Format</span></span>

<span data-ttu-id="f0c0f-206">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-207">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-207">Pattern</span></span>

<span data-ttu-id="f0c0f-208">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-209">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-209">Checksum</span></span>

<span data-ttu-id="f0c0f-210">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-211">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-211">Definition</span></span>

<span data-ttu-id="f0c0f-212">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-213">Der reguläre Ausdruck `Regex_czech_republic_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-214">Ein Schlüsselwort `Keywords_czech_republic_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-215">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-215">Keywords</span></span>

<span data-ttu-id="f0c0f-216">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-216"></span></span>
|<span data-ttu-id="f0c0f-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-218">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-218">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-219">Tschechische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-219">czech passport number</span></span>  <br/> <span data-ttu-id="f0c0f-220">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-220">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-221">Cestovní Pas</span><span class="sxs-lookup"><span data-stu-id="f0c0f-221">cestovní pas</span></span>  <br/> <span data-ttu-id="f0c0f-222">Pas</span><span class="sxs-lookup"><span data-stu-id="f0c0f-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="f0c0f-223">Dänemark</span><span class="sxs-lookup"><span data-stu-id="f0c0f-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-224">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-224">Format</span></span>

<span data-ttu-id="f0c0f-225">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-226">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-226">Pattern</span></span>

 <span data-ttu-id="f0c0f-227">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-228">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-228">Checksum</span></span>

<span data-ttu-id="f0c0f-229">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-230">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-230">Definition</span></span>

<span data-ttu-id="f0c0f-231">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-232">Der reguläre Ausdruck `Regex_denmark_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-233">Ein Schlüsselwort `Keywords_denmark_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-234">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-234">Keywords</span></span>

<span data-ttu-id="f0c0f-235">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-235"></span></span>
|<span data-ttu-id="f0c0f-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-237">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-237">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-238">dänische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-238">danish passport number</span></span>  <br/> <span data-ttu-id="f0c0f-239">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-239">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-240">Pas</span><span class="sxs-lookup"><span data-stu-id="f0c0f-240">pas</span></span>  <br/> <span data-ttu-id="f0c0f-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="f0c0f-242">Estland</span><span class="sxs-lookup"><span data-stu-id="f0c0f-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-243">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-243">Format</span></span>

<span data-ttu-id="f0c0f-244">Ein Buchstabe, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-245">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-245">Pattern</span></span>

<span data-ttu-id="f0c0f-246">Ein Buchstabe, gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-247">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-247">Checksum</span></span>

<span data-ttu-id="f0c0f-248">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-249">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-249">Definition</span></span>

<span data-ttu-id="f0c0f-250">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-251">Der reguläre Ausdruck `Regex_estonia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-252">Ein Schlüsselwort `Keywords_estonia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-253">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-253">Keywords</span></span>

<span data-ttu-id="f0c0f-254">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-254"></span></span>
|<span data-ttu-id="f0c0f-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-256">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-256">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-257">Estnische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-257">estonian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-258">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-258">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="f0c0f-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="f0c0f-260">Finnland</span><span class="sxs-lookup"><span data-stu-id="f0c0f-260">Finland</span></span>

<span data-ttu-id="f0c0f-261">Ausführliche Informationen finden Sie im Abschnitt "Finnland-Passport-Nummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f0c0f-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="f0c0f-262">Frankreich</span><span class="sxs-lookup"><span data-stu-id="f0c0f-262">France</span></span>

<span data-ttu-id="f0c0f-263">Ausführliche Informationen finden Sie im Abschnitt "französische Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f0c0f-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="f0c0f-264">Deutschland</span><span class="sxs-lookup"><span data-stu-id="f0c0f-264">Germany</span></span>

<span data-ttu-id="f0c0f-265">Ausführliche Informationen finden Sie im Abschnitt "Deutsche Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f0c0f-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="f0c0f-266">Griechenland</span><span class="sxs-lookup"><span data-stu-id="f0c0f-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-267">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-267">Format</span></span>

<span data-ttu-id="f0c0f-268">Zwei Buchstaben, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-269">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-269">Pattern</span></span>

<span data-ttu-id="f0c0f-270">Zwei Buchstaben gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-271">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-271">Checksum</span></span>

<span data-ttu-id="f0c0f-272">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-273">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-273">Definition</span></span>

<span data-ttu-id="f0c0f-274">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-275">Der reguläre Ausdruck `Regex_greece_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-276">Ein Schlüsselwort `Keywords_greece_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-277">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-277">Keywords</span></span>

<span data-ttu-id="f0c0f-278">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-278"></span></span>
|<span data-ttu-id="f0c0f-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-280">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-280">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-281">griechische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-281">greek passport number</span></span>  <br/> <span data-ttu-id="f0c0f-282">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-282">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="f0c0f-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="f0c0f-284">Ungarn</span><span class="sxs-lookup"><span data-stu-id="f0c0f-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-285">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-285">Format</span></span>

<span data-ttu-id="f0c0f-286">Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-287">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-287">Pattern</span></span>

<span data-ttu-id="f0c0f-288">Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-289">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-289">Checksum</span></span>

<span data-ttu-id="f0c0f-290">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-291">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-291">Definition</span></span>

<span data-ttu-id="f0c0f-292">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-293">Der reguläre Ausdruck `Regex_hungary_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-294">Ein Schlüsselwort `Keywords_hungary_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-295">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-295">Keywords</span></span>

<span data-ttu-id="f0c0f-296">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-296"></span></span>
|<span data-ttu-id="f0c0f-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-298">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-298">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-299">ungarische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-300">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-300">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="f0c0f-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="f0c0f-302">Irland</span><span class="sxs-lookup"><span data-stu-id="f0c0f-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-303">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-303">Format</span></span>

<span data-ttu-id="f0c0f-304">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-305">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-305">Pattern</span></span>

<span data-ttu-id="f0c0f-306">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="f0c0f-307">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="f0c0f-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="f0c0f-308">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0c0f-309">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-309">Checksum</span></span>

<span data-ttu-id="f0c0f-310">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-311">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-311">Definition</span></span>

<span data-ttu-id="f0c0f-312">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-313">Der reguläre Ausdruck `Regex_ireland_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-314">Ein Schlüsselwort `Keywords_ireland_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-315">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-315">Keywords</span></span>

<span data-ttu-id="f0c0f-316">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-316"></span></span>
|<span data-ttu-id="f0c0f-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-318">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-318">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-319">irische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-319">irish passport number</span></span>  <br/> <span data-ttu-id="f0c0f-320">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-320">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-321">Pas</span><span class="sxs-lookup"><span data-stu-id="f0c0f-321">pas</span></span>  <br/> <span data-ttu-id="f0c0f-322">Pass</span><span class="sxs-lookup"><span data-stu-id="f0c0f-322">passport</span></span>  <br/> <span data-ttu-id="f0c0f-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="f0c0f-323">passeport</span></span>  <br/> <span data-ttu-id="f0c0f-324">Passeport numero</span><span class="sxs-lookup"><span data-stu-id="f0c0f-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="f0c0f-325">Italien</span><span class="sxs-lookup"><span data-stu-id="f0c0f-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-326">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-326">Format</span></span>

<span data-ttu-id="f0c0f-327">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-328">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-328">Pattern</span></span>

<span data-ttu-id="f0c0f-329">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="f0c0f-330">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="f0c0f-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="f0c0f-331">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0c0f-332">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-332">Checksum</span></span>

<span data-ttu-id="f0c0f-333">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="f0c0f-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-334">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-334">Definition</span></span>

<span data-ttu-id="f0c0f-335">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-336">Der reguläre Ausdruck `Regex_italy_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-337">Ein Schlüsselwort `Keywords_italy_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-338">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-338">Keywords</span></span>

<span data-ttu-id="f0c0f-339">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-339"></span></span>
|<span data-ttu-id="f0c0f-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-341">italienische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-341">italian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-342">Repubblica Italiana Passa Porto</span><span class="sxs-lookup"><span data-stu-id="f0c0f-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="f0c0f-343">Passa Porto</span><span class="sxs-lookup"><span data-stu-id="f0c0f-343">passaporto</span></span>  <br/> <span data-ttu-id="f0c0f-344">Passa Porto Italiana</span><span class="sxs-lookup"><span data-stu-id="f0c0f-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="f0c0f-345">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-345">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-346">Italiana Passa Porto numero</span><span class="sxs-lookup"><span data-stu-id="f0c0f-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="f0c0f-347">Passa Porto numero</span><span class="sxs-lookup"><span data-stu-id="f0c0f-347">passaporto numero</span></span>  <br/> <span data-ttu-id="f0c0f-348">Numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="f0c0f-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="f0c0f-349">Numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="f0c0f-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="f0c0f-350">Lettland</span><span class="sxs-lookup"><span data-stu-id="f0c0f-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-351">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-351">Format</span></span>

<span data-ttu-id="f0c0f-352">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-353">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-353">Pattern</span></span>

<span data-ttu-id="f0c0f-354">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="f0c0f-355">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="f0c0f-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="f0c0f-356">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0c0f-357">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-357">Checksum</span></span>

<span data-ttu-id="f0c0f-358">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-359">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-359">Definition</span></span>

<span data-ttu-id="f0c0f-360">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-361">Der reguläre Ausdruck `Regex_latvia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-362">Ein Schlüsselwort `Keywords_latvia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-363">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-363">Keywords</span></span>

<span data-ttu-id="f0c0f-364">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-364"></span></span>
|<span data-ttu-id="f0c0f-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-366">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-366">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-367">Lettische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-367">latvian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-368">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-368">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-369">Pase numurs</span><span class="sxs-lookup"><span data-stu-id="f0c0f-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="f0c0f-370">Litauen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-371">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-371">Format</span></span>

<span data-ttu-id="f0c0f-372">Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-373">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-373">Pattern</span></span>

<span data-ttu-id="f0c0f-374">Acht Ziffern oder Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="f0c0f-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-375">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-375">Checksum</span></span>

<span data-ttu-id="f0c0f-376">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="f0c0f-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-377">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-377">Definition</span></span>

<span data-ttu-id="f0c0f-378">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-379">Der reguläre Ausdruck `Regex_lithuania_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-380">Ein Schlüsselwort `Keywords_lithuania_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-381">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-381">Keywords</span></span>

<span data-ttu-id="f0c0f-382">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-382"></span></span>
|<span data-ttu-id="f0c0f-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-384">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-384">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-385">lithunian Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-386">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-386">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-387">Paso Numeris</span><span class="sxs-lookup"><span data-stu-id="f0c0f-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="f0c0f-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="f0c0f-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-389">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-389">Format</span></span>

<span data-ttu-id="f0c0f-390">Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-391">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-391">Pattern</span></span>

<span data-ttu-id="f0c0f-392">Acht Ziffern oder Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="f0c0f-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-393">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-393">Checksum</span></span>

<span data-ttu-id="f0c0f-394">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-395">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-395">Definition</span></span>

<span data-ttu-id="f0c0f-396">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-397">Der reguläre Ausdruck `Regex_nation_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-398">Ein Schlüsselwort `Keywords_nation_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-399">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-399">Keywords</span></span>

<span data-ttu-id="f0c0f-400">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-400"></span></span>
|<span data-ttu-id="f0c0f-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-402">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-402">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-403">Lettische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-403">latvian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-404">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-404">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="f0c0f-406">Malta</span><span class="sxs-lookup"><span data-stu-id="f0c0f-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-407">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-407">Format</span></span>

<span data-ttu-id="f0c0f-408">Sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-409">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-409">Pattern</span></span>

 <span data-ttu-id="f0c0f-410">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-411">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-411">Checksum</span></span>

<span data-ttu-id="f0c0f-412">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-413">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-413">Definition</span></span>

<span data-ttu-id="f0c0f-414">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-415">Der reguläre Ausdruck `Regex_malta_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-416">Ein Schlüsselwort `Keywords_malta_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-417">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-417">Keywords</span></span>

<span data-ttu-id="f0c0f-418">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-418"></span></span>
|<span data-ttu-id="f0c0f-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-420">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-420">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-421">Maltesische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-421">maltese passport number</span></span>  <br/> <span data-ttu-id="f0c0f-422">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-422">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-423">numru Tal-Passaport</span><span class="sxs-lookup"><span data-stu-id="f0c0f-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="f0c0f-424">Niederlande</span><span class="sxs-lookup"><span data-stu-id="f0c0f-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-425">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-425">Format</span></span>

<span data-ttu-id="f0c0f-426">Neun Buchstaben oder Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-427">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-427">Pattern</span></span>

<span data-ttu-id="f0c0f-428">Neun Buchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-429">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-429">Checksum</span></span>

<span data-ttu-id="f0c0f-430">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="f0c0f-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-431">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-431">Definition</span></span>

<span data-ttu-id="f0c0f-432">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-433">Der reguläre Ausdruck `Regex_netherlands_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-434">Ein Schlüsselwort `Keywords_netherlands_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-435">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-435">Keywords</span></span>

<span data-ttu-id="f0c0f-436">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-436"></span></span>
|<span data-ttu-id="f0c0f-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-438">niederländische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-438">dutch passport number</span></span>  <br/> <span data-ttu-id="f0c0f-439">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-439">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-440">niederländische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="f0c0f-441">Nederlanden paspoort Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="f0c0f-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="f0c0f-442">paspoort</span></span>  <br/> <span data-ttu-id="f0c0f-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="f0c0f-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="f0c0f-445">Polen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-445">Poland</span></span>

<span data-ttu-id="f0c0f-446">Ausführliche Informationen finden Sie im Abschnitt "Polen-Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f0c0f-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="f0c0f-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="f0c0f-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-448">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-448">Format</span></span>

<span data-ttu-id="f0c0f-449">Ein Buchstabe, gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-450">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-450">Pattern</span></span>

<span data-ttu-id="f0c0f-451">Ein Buchstabe, gefolgt von sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="f0c0f-452">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="f0c0f-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="f0c0f-453">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0c0f-454">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-454">Checksum</span></span>

<span data-ttu-id="f0c0f-455">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-456">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-456">Definition</span></span>

<span data-ttu-id="f0c0f-457">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-458">Der reguläre Ausdruck `Regex_portugal_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-459">Ein Schlüsselwort `Keywords_portugal_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-460">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-460">Keywords</span></span>

<span data-ttu-id="f0c0f-461">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-461"></span></span>
|<span data-ttu-id="f0c0f-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-463">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-463">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-464">portugiesische Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="f0c0f-465">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-465">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="f0c0f-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="f0c0f-467">Rumänien</span><span class="sxs-lookup"><span data-stu-id="f0c0f-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-468">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-468">Format</span></span>

<span data-ttu-id="f0c0f-469">Acht oder neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-470">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-470">Pattern</span></span>

<span data-ttu-id="f0c0f-471">Acht oder neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-472">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-472">Checksum</span></span>

<span data-ttu-id="f0c0f-473">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-474">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-474">Definition</span></span>

<span data-ttu-id="f0c0f-475">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-476">Der reguläre Ausdruck `Regex_romania_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-477">Ein Schlüsselwort `Keywords_romania_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-478">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-478">Keywords</span></span>

<span data-ttu-id="f0c0f-479">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-479"></span></span>
|<span data-ttu-id="f0c0f-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-481">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-481">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-482">rumänische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-482">romanian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-483">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-483">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="f0c0f-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="f0c0f-485">Slowakei</span><span class="sxs-lookup"><span data-stu-id="f0c0f-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-486">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-486">Format</span></span>

<span data-ttu-id="f0c0f-487">Eine Ziffer oder ein Buchstabe, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-488">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-488">Pattern</span></span>

<span data-ttu-id="f0c0f-489">Eine Ziffer oder ein Buchstabe (ohne Groß-/Kleinschreibung), gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f0c0f-490">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-490">Checksum</span></span>

<span data-ttu-id="f0c0f-491">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-492">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-492">Definition</span></span>

<span data-ttu-id="f0c0f-493">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-494">Der reguläre Ausdruck `Regex_slovakia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-495">Ein Schlüsselwort `Keywords_slovakia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-496">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-496">Keywords</span></span>

<span data-ttu-id="f0c0f-497">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-497"></span></span>
|<span data-ttu-id="f0c0f-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-499">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-499">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-500">Slowakische Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-501">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-501">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="f0c0f-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="f0c0f-503">Slowenien</span><span class="sxs-lookup"><span data-stu-id="f0c0f-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-504">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-504">Format</span></span>

<span data-ttu-id="f0c0f-505">Zwei Buchstaben, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-506">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-506">Pattern</span></span>

<span data-ttu-id="f0c0f-507">Zwei Buchstaben, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="f0c0f-508">Der Buchstabe "P"</span><span class="sxs-lookup"><span data-stu-id="f0c0f-508">The letter "P"</span></span>
    
- <span data-ttu-id="f0c0f-509">Ein Großbuchstabe</span><span class="sxs-lookup"><span data-stu-id="f0c0f-509">One uppercase letter</span></span>
    
- <span data-ttu-id="f0c0f-510">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0c0f-511">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-511">Checksum</span></span>

<span data-ttu-id="f0c0f-512">Nein</span><span class="sxs-lookup"><span data-stu-id="f0c0f-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-513">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-513">Definition</span></span>

<span data-ttu-id="f0c0f-514">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-515">Der reguläre Ausdruck `Regex_slovenia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-516">Ein Schlüsselwort `Keywords_slovenia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-517">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-517">Keywords</span></span>

<span data-ttu-id="f0c0f-518">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-518"></span></span>
|<span data-ttu-id="f0c0f-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-520">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-520">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-521">slowenische Passnummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="f0c0f-522">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-522">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="f0c0f-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="f0c0f-524">Spanien</span><span class="sxs-lookup"><span data-stu-id="f0c0f-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="f0c0f-525">Format</span><span class="sxs-lookup"><span data-stu-id="f0c0f-525">Format</span></span>

<span data-ttu-id="f0c0f-526">Eine Kombination aus Buchstaben und Zahlen mit acht oder neun Zeichen ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f0c0f-527">Muster</span><span class="sxs-lookup"><span data-stu-id="f0c0f-527">Pattern</span></span>

<span data-ttu-id="f0c0f-528">Eine Kombination aus Buchstaben und Zahlen aus acht oder neun Zeichen:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="f0c0f-529">Zwei Ziffern oder Buchstaben</span><span class="sxs-lookup"><span data-stu-id="f0c0f-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="f0c0f-530">Eine Ziffer oder ein Buchstabe (optional)</span><span class="sxs-lookup"><span data-stu-id="f0c0f-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="f0c0f-531">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="f0c0f-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f0c0f-532">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="f0c0f-532">Checksum</span></span>

<span data-ttu-id="f0c0f-533">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="f0c0f-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f0c0f-534">Definition</span><span class="sxs-lookup"><span data-stu-id="f0c0f-534">Definition</span></span>

<span data-ttu-id="f0c0f-535">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f0c0f-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f0c0f-536">Der reguläre Ausdruck `Regex_spain_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f0c0f-537">Ein Schlüsselwort `Keywords_spain_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f0c0f-538">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0c0f-538">Keywords</span></span>

<span data-ttu-id="f0c0f-539">| |</span><span class="sxs-lookup"><span data-stu-id="f0c0f-539"></span></span>
|<span data-ttu-id="f0c0f-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="f0c0f-541">Pass</span><span class="sxs-lookup"><span data-stu-id="f0c0f-541">passport</span></span>  <br/> <span data-ttu-id="f0c0f-542">Spanien-Passport</span><span class="sxs-lookup"><span data-stu-id="f0c0f-542">spain passport</span></span>  <br/> <span data-ttu-id="f0c0f-543">Passport-Buch</span><span class="sxs-lookup"><span data-stu-id="f0c0f-543">passport book</span></span>  <br/> <span data-ttu-id="f0c0f-544">passport number</span><span class="sxs-lookup"><span data-stu-id="f0c0f-544">passport number</span></span>  <br/> <span data-ttu-id="f0c0f-545">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="f0c0f-545">passport no</span></span>  <br/> <span data-ttu-id="f0c0f-546">Libreta Pasaporte</span><span class="sxs-lookup"><span data-stu-id="f0c0f-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="f0c0f-547">número Pasaporte</span><span class="sxs-lookup"><span data-stu-id="f0c0f-547">número pasaporte</span></span>  <br/> <span data-ttu-id="f0c0f-548">ESPAÑA PASAPORTE</span><span class="sxs-lookup"><span data-stu-id="f0c0f-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="f0c0f-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="f0c0f-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="f0c0f-550">Schweden</span><span class="sxs-lookup"><span data-stu-id="f0c0f-550">Sweden</span></span>

<span data-ttu-id="f0c0f-551">Ausführliche Informationen finden Sie im Abschnitt "schwedische Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f0c0f-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="f0c0f-552">UK</span><span class="sxs-lookup"><span data-stu-id="f0c0f-552">UK</span></span>

<span data-ttu-id="f0c0f-553">Ausführliche Informationen finden Sie im Abschnitt "U.S./U.K.</span><span class="sxs-lookup"><span data-stu-id="f0c0f-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="f0c0f-554">Passport-Nummer "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f0c0f-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f0c0f-555">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0c0f-555">See also</span></span>

[<span data-ttu-id="f0c0f-556">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="f0c0f-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

