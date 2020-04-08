---
title: EU-Passport-Nummer
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 0032d3e50d7dab0b696d9000242e70956469052e
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "41592116"
---
# <a name="eu-passport-number"></a><span data-ttu-id="80a95-104">EU-Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-104">EU Passport Number</span></span>

<span data-ttu-id="80a95-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp EU-Passport-Nummern erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="80a95-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="80a95-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="80a95-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="80a95-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="80a95-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="80a95-108">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-108">Format</span></span>

<span data-ttu-id="80a95-109">Ein Buchstabe, gefolgt von einem optionalen Leerzeichen und sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-110">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-110">Pattern</span></span>

<span data-ttu-id="80a95-111">Eine Kombination aus einem Buchstaben, sieben Ziffern und einem Leerzeichen:</span><span class="sxs-lookup"><span data-stu-id="80a95-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="80a95-112">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="80a95-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="80a95-113">Ein Leerzeichen (optional)</span><span class="sxs-lookup"><span data-stu-id="80a95-113">One space (optional)</span></span>
    
- <span data-ttu-id="80a95-114">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="80a95-115">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-115">Checksum</span></span>

<span data-ttu-id="80a95-116">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="80a95-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-117">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-117">Definition</span></span>

<span data-ttu-id="80a95-118">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-119">Der reguläre Ausdruck `Regex_austria_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-120">Ein Schlüsselwort `Keywords_austria_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-121">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-121">Keywords</span></span>

<span data-ttu-id="80a95-122">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-122">| |</span></span>
|<span data-ttu-id="80a95-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-124">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-124">passport number</span></span>  <br/> <span data-ttu-id="80a95-125">Österreichische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-125">austrian passport number</span></span>  <br/> <span data-ttu-id="80a95-126">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-126">passport no</span></span>  <br/> <span data-ttu-id="80a95-127">Reisepass</span><span class="sxs-lookup"><span data-stu-id="80a95-127">reisepass</span></span>  <br/> <span data-ttu-id="80a95-128">österreichisch Reisepass</span><span class="sxs-lookup"><span data-stu-id="80a95-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="80a95-129">Belgien</span><span class="sxs-lookup"><span data-stu-id="80a95-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="80a95-130">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-130">Format</span></span>

<span data-ttu-id="80a95-131">Zwei Buchstaben, gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-132">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-132">Pattern</span></span>

<span data-ttu-id="80a95-133">Zwei Buchstaben und gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="80a95-134">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-134">Checksum</span></span>

<span data-ttu-id="80a95-135">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="80a95-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-136">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-136">Definition</span></span>

<span data-ttu-id="80a95-137">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-138">Der reguläre Ausdruck `Regex_belgium_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-139">Ein Schlüsselwort `Keywords_belgium_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-140">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-140">Keywords</span></span>

<span data-ttu-id="80a95-141">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-141">| |</span></span>
|<span data-ttu-id="80a95-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-143">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-143">passport number</span></span>  <br/> <span data-ttu-id="80a95-144">belgische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-144">belgian passport number</span></span>  <br/> <span data-ttu-id="80a95-145">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-145">passport no</span></span>  <br/> <span data-ttu-id="80a95-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="80a95-146">paspoort</span></span>  <br/> <span data-ttu-id="80a95-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="80a95-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="80a95-148">reisepass kein</span></span>  <br/> <span data-ttu-id="80a95-149">Reisepass</span><span class="sxs-lookup"><span data-stu-id="80a95-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="80a95-150">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="80a95-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="80a95-151">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-151">Format</span></span>

<span data-ttu-id="80a95-152">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-153">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-153">Pattern</span></span>

 <span data-ttu-id="80a95-154">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="80a95-155">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-155">Checksum</span></span>

<span data-ttu-id="80a95-156">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-157">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-157">Definition</span></span>

<span data-ttu-id="80a95-158">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-159">Der reguläre Ausdruck `Regex_bulgaria_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-160">Ein Schlüsselwort `Keywords_bulgaria_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-161">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-161">Keywords</span></span>

<span data-ttu-id="80a95-162">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-162">| |</span></span>
|<span data-ttu-id="80a95-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-164">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-164">passport number</span></span>  <br/> <span data-ttu-id="80a95-165">Bulgarische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="80a95-166">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-166">passport no</span></span>  <br/> <span data-ttu-id="80a95-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="80a95-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="80a95-168">Kroatien</span><span class="sxs-lookup"><span data-stu-id="80a95-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="80a95-169">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-169">Format</span></span>

<span data-ttu-id="80a95-170">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-171">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-171">Pattern</span></span>

 <span data-ttu-id="80a95-172">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="80a95-173">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-173">Checksum</span></span>

<span data-ttu-id="80a95-174">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-175">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-175">Definition</span></span>

<span data-ttu-id="80a95-176">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-177">Der reguläre Ausdruck `Regex_croatia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-178">Ein Schlüsselwort `Keywords_croatia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-179">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-179">Keywords</span></span>

<span data-ttu-id="80a95-180">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-180">| |</span></span>
|<span data-ttu-id="80a95-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-182">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-182">passport number</span></span>  <br/> <span data-ttu-id="80a95-183">Kroatische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-183">croatian passport number</span></span>  <br/> <span data-ttu-id="80a95-184">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-184">passport no</span></span>  <br/> <span data-ttu-id="80a95-185">Broj putovnice</span><span class="sxs-lookup"><span data-stu-id="80a95-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="80a95-186">Zypern</span><span class="sxs-lookup"><span data-stu-id="80a95-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="80a95-187">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-187">Format</span></span>

<span data-ttu-id="80a95-188">Ein Buchstabe, gefolgt von 6-8 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-189">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-189">Pattern</span></span>

<span data-ttu-id="80a95-190">Ein Buchstabe, gefolgt von sechs bis acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="80a95-191">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-191">Checksum</span></span>

<span data-ttu-id="80a95-192">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-193">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-193">Definition</span></span>

<span data-ttu-id="80a95-194">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-195">Der reguläre Ausdruck `Regex_cyprus_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-196">Ein Schlüsselwort `Keywords_cyprus_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-197">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-197">Keywords</span></span>

<span data-ttu-id="80a95-198">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-198">| |</span></span>
|<span data-ttu-id="80a95-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-200">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-200">passport number</span></span>  <br/> <span data-ttu-id="80a95-201">Zypern-Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="80a95-202">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-202">passport no</span></span>  <br/> <span data-ttu-id="80a95-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="80a95-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="80a95-204">Tschechien</span><span class="sxs-lookup"><span data-stu-id="80a95-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="80a95-205">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-205">Format</span></span>

<span data-ttu-id="80a95-206">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-207">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-207">Pattern</span></span>

<span data-ttu-id="80a95-208">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="80a95-209">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-209">Checksum</span></span>

<span data-ttu-id="80a95-210">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-211">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-211">Definition</span></span>

<span data-ttu-id="80a95-212">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-213">Der reguläre Ausdruck `Regex_czech_republic_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-214">Ein Schlüsselwort `Keywords_czech_republic_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-215">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-215">Keywords</span></span>

<span data-ttu-id="80a95-216">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-216">| |</span></span>
|<span data-ttu-id="80a95-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-218">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-218">passport number</span></span>  <br/> <span data-ttu-id="80a95-219">Tschechische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-219">czech passport number</span></span>  <br/> <span data-ttu-id="80a95-220">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-220">passport no</span></span>  <br/> <span data-ttu-id="80a95-221">Cestovní Pas</span><span class="sxs-lookup"><span data-stu-id="80a95-221">cestovní pas</span></span>  <br/> <span data-ttu-id="80a95-222">Pas</span><span class="sxs-lookup"><span data-stu-id="80a95-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="80a95-223">Dänemark</span><span class="sxs-lookup"><span data-stu-id="80a95-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="80a95-224">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-224">Format</span></span>

<span data-ttu-id="80a95-225">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-226">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-226">Pattern</span></span>

 <span data-ttu-id="80a95-227">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="80a95-228">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-228">Checksum</span></span>

<span data-ttu-id="80a95-229">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-230">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-230">Definition</span></span>

<span data-ttu-id="80a95-231">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-232">Der reguläre Ausdruck `Regex_denmark_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-233">Ein Schlüsselwort `Keywords_denmark_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-234">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-234">Keywords</span></span>

<span data-ttu-id="80a95-235">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-235">| |</span></span>
|<span data-ttu-id="80a95-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-237">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-237">passport number</span></span>  <br/> <span data-ttu-id="80a95-238">dänische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-238">danish passport number</span></span>  <br/> <span data-ttu-id="80a95-239">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-239">passport no</span></span>  <br/> <span data-ttu-id="80a95-240">Pas</span><span class="sxs-lookup"><span data-stu-id="80a95-240">pas</span></span>  <br/> <span data-ttu-id="80a95-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="80a95-242">Estland</span><span class="sxs-lookup"><span data-stu-id="80a95-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="80a95-243">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-243">Format</span></span>

<span data-ttu-id="80a95-244">Ein Buchstabe, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-245">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-245">Pattern</span></span>

<span data-ttu-id="80a95-246">Ein Buchstabe, gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="80a95-247">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-247">Checksum</span></span>

<span data-ttu-id="80a95-248">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-249">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-249">Definition</span></span>

<span data-ttu-id="80a95-250">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-251">Der reguläre Ausdruck `Regex_estonia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-252">Ein Schlüsselwort `Keywords_estonia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-253">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-253">Keywords</span></span>

<span data-ttu-id="80a95-254">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-254">| |</span></span>
|<span data-ttu-id="80a95-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-256">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-256">passport number</span></span>  <br/> <span data-ttu-id="80a95-257">Estnische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-257">estonian passport number</span></span>  <br/> <span data-ttu-id="80a95-258">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-258">passport no</span></span>  <br/> <span data-ttu-id="80a95-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="80a95-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="80a95-260">Finnland</span><span class="sxs-lookup"><span data-stu-id="80a95-260">Finland</span></span>

<span data-ttu-id="80a95-261">Ausführliche Informationen finden Sie im Abschnitt "Finnland-Passport-Nummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="80a95-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="80a95-262">Frankreich</span><span class="sxs-lookup"><span data-stu-id="80a95-262">France</span></span>

<span data-ttu-id="80a95-263">Ausführliche Informationen finden Sie im Abschnitt "französische Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="80a95-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="80a95-264">Deutschland</span><span class="sxs-lookup"><span data-stu-id="80a95-264">Germany</span></span>

<span data-ttu-id="80a95-265">Ausführliche Informationen finden Sie im Abschnitt "Deutsche Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="80a95-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="80a95-266">Griechenland</span><span class="sxs-lookup"><span data-stu-id="80a95-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="80a95-267">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-267">Format</span></span>

<span data-ttu-id="80a95-268">Zwei Buchstaben, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-269">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-269">Pattern</span></span>

<span data-ttu-id="80a95-270">Zwei Buchstaben gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="80a95-271">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-271">Checksum</span></span>

<span data-ttu-id="80a95-272">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-273">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-273">Definition</span></span>

<span data-ttu-id="80a95-274">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-275">Der reguläre Ausdruck `Regex_greece_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-276">Ein Schlüsselwort `Keywords_greece_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-277">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-277">Keywords</span></span>

<span data-ttu-id="80a95-278">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-278">| |</span></span>
|<span data-ttu-id="80a95-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-280">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-280">passport number</span></span>  <br/> <span data-ttu-id="80a95-281">griechische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-281">greek passport number</span></span>  <br/> <span data-ttu-id="80a95-282">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-282">passport no</span></span>  <br/> <span data-ttu-id="80a95-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="80a95-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="80a95-284">Ungarn</span><span class="sxs-lookup"><span data-stu-id="80a95-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="80a95-285">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-285">Format</span></span>

<span data-ttu-id="80a95-286">Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-287">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-287">Pattern</span></span>

<span data-ttu-id="80a95-288">Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="80a95-289">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-289">Checksum</span></span>

<span data-ttu-id="80a95-290">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-291">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-291">Definition</span></span>

<span data-ttu-id="80a95-292">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-293">Der reguläre Ausdruck `Regex_hungary_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-294">Ein Schlüsselwort `Keywords_hungary_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-295">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-295">Keywords</span></span>

<span data-ttu-id="80a95-296">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-296">| |</span></span>
|<span data-ttu-id="80a95-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-298">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-298">passport number</span></span>  <br/> <span data-ttu-id="80a95-299">ungarische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="80a95-300">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-300">passport no</span></span>  <br/> <span data-ttu-id="80a95-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="80a95-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="80a95-302">Irland</span><span class="sxs-lookup"><span data-stu-id="80a95-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="80a95-303">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-303">Format</span></span>

<span data-ttu-id="80a95-304">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-305">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-305">Pattern</span></span>

<span data-ttu-id="80a95-306">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="80a95-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="80a95-307">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="80a95-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="80a95-308">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="80a95-309">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-309">Checksum</span></span>

<span data-ttu-id="80a95-310">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-311">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-311">Definition</span></span>

<span data-ttu-id="80a95-312">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-313">Der reguläre Ausdruck `Regex_ireland_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-314">Ein Schlüsselwort `Keywords_ireland_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-315">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-315">Keywords</span></span>

<span data-ttu-id="80a95-316">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-316">| |</span></span>
|<span data-ttu-id="80a95-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-318">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-318">passport number</span></span>  <br/> <span data-ttu-id="80a95-319">irische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-319">irish passport number</span></span>  <br/> <span data-ttu-id="80a95-320">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-320">passport no</span></span>  <br/> <span data-ttu-id="80a95-321">Pas</span><span class="sxs-lookup"><span data-stu-id="80a95-321">pas</span></span>  <br/> <span data-ttu-id="80a95-322">Pass</span><span class="sxs-lookup"><span data-stu-id="80a95-322">passport</span></span>  <br/> <span data-ttu-id="80a95-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="80a95-323">passeport</span></span>  <br/> <span data-ttu-id="80a95-324">Passeport numero</span><span class="sxs-lookup"><span data-stu-id="80a95-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="80a95-325">Italien</span><span class="sxs-lookup"><span data-stu-id="80a95-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="80a95-326">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-326">Format</span></span>

<span data-ttu-id="80a95-327">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-328">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-328">Pattern</span></span>

<span data-ttu-id="80a95-329">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="80a95-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="80a95-330">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="80a95-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="80a95-331">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="80a95-332">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-332">Checksum</span></span>

<span data-ttu-id="80a95-333">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="80a95-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-334">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-334">Definition</span></span>

<span data-ttu-id="80a95-335">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-336">Der reguläre Ausdruck `Regex_italy_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-337">Ein Schlüsselwort `Keywords_italy_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-338">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-338">Keywords</span></span>

<span data-ttu-id="80a95-339">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-339">| |</span></span>
|<span data-ttu-id="80a95-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-341">italienische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-341">italian passport number</span></span>  <br/> <span data-ttu-id="80a95-342">Repubblica Italiana Passa Porto</span><span class="sxs-lookup"><span data-stu-id="80a95-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="80a95-343">Passa Porto</span><span class="sxs-lookup"><span data-stu-id="80a95-343">passaporto</span></span>  <br/> <span data-ttu-id="80a95-344">Passa Porto Italiana</span><span class="sxs-lookup"><span data-stu-id="80a95-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="80a95-345">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-345">passport number</span></span>  <br/> <span data-ttu-id="80a95-346">Italiana Passa Porto numero</span><span class="sxs-lookup"><span data-stu-id="80a95-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="80a95-347">Passa Porto numero</span><span class="sxs-lookup"><span data-stu-id="80a95-347">passaporto numero</span></span>  <br/> <span data-ttu-id="80a95-348">Numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="80a95-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="80a95-349">Numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="80a95-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="80a95-350">Lettland</span><span class="sxs-lookup"><span data-stu-id="80a95-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="80a95-351">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-351">Format</span></span>

<span data-ttu-id="80a95-352">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-353">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-353">Pattern</span></span>

<span data-ttu-id="80a95-354">Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="80a95-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="80a95-355">Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="80a95-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="80a95-356">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="80a95-357">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-357">Checksum</span></span>

<span data-ttu-id="80a95-358">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-359">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-359">Definition</span></span>

<span data-ttu-id="80a95-360">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-361">Der reguläre Ausdruck `Regex_latvia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-362">Ein Schlüsselwort `Keywords_latvia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-363">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-363">Keywords</span></span>

<span data-ttu-id="80a95-364">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-364">| |</span></span>
|<span data-ttu-id="80a95-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-366">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-366">passport number</span></span>  <br/> <span data-ttu-id="80a95-367">Lettische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-367">latvian passport number</span></span>  <br/> <span data-ttu-id="80a95-368">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-368">passport no</span></span>  <br/> <span data-ttu-id="80a95-369">Pase numurs</span><span class="sxs-lookup"><span data-stu-id="80a95-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="80a95-370">Litauen</span><span class="sxs-lookup"><span data-stu-id="80a95-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="80a95-371">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-371">Format</span></span>

<span data-ttu-id="80a95-372">Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-373">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-373">Pattern</span></span>

<span data-ttu-id="80a95-374">Acht Ziffern oder Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="80a95-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="80a95-375">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-375">Checksum</span></span>

<span data-ttu-id="80a95-376">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="80a95-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-377">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-377">Definition</span></span>

<span data-ttu-id="80a95-378">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-379">Der reguläre Ausdruck `Regex_lithuania_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-380">Ein Schlüsselwort `Keywords_lithuania_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-381">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-381">Keywords</span></span>

<span data-ttu-id="80a95-382">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-382">| |</span></span>
|<span data-ttu-id="80a95-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-384">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-384">passport number</span></span>  <br/> <span data-ttu-id="80a95-385">lithunian Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="80a95-386">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-386">passport no</span></span>  <br/> <span data-ttu-id="80a95-387">Paso Numeris</span><span class="sxs-lookup"><span data-stu-id="80a95-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="80a95-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="80a95-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="80a95-389">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-389">Format</span></span>

<span data-ttu-id="80a95-390">Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-391">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-391">Pattern</span></span>

<span data-ttu-id="80a95-392">Acht Ziffern oder Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="80a95-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="80a95-393">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-393">Checksum</span></span>

<span data-ttu-id="80a95-394">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-395">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-395">Definition</span></span>

<span data-ttu-id="80a95-396">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-397">Der reguläre Ausdruck `Regex_nation_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-398">Ein Schlüsselwort `Keywords_nation_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-399">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-399">Keywords</span></span>

<span data-ttu-id="80a95-400">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-400">| |</span></span>
|<span data-ttu-id="80a95-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-402">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-402">passport number</span></span>  <br/> <span data-ttu-id="80a95-403">Lettische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-403">latvian passport number</span></span>  <br/> <span data-ttu-id="80a95-404">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-404">passport no</span></span>  <br/> <span data-ttu-id="80a95-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="80a95-406">Malta</span><span class="sxs-lookup"><span data-stu-id="80a95-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="80a95-407">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-407">Format</span></span>

<span data-ttu-id="80a95-408">Sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-409">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-409">Pattern</span></span>

 <span data-ttu-id="80a95-410">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="80a95-411">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-411">Checksum</span></span>

<span data-ttu-id="80a95-412">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-413">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-413">Definition</span></span>

<span data-ttu-id="80a95-414">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-415">Der reguläre Ausdruck `Regex_malta_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-416">Ein Schlüsselwort `Keywords_malta_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-417">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-417">Keywords</span></span>

<span data-ttu-id="80a95-418">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-418">| |</span></span>
|<span data-ttu-id="80a95-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-420">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-420">passport number</span></span>  <br/> <span data-ttu-id="80a95-421">Maltesische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-421">maltese passport number</span></span>  <br/> <span data-ttu-id="80a95-422">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-422">passport no</span></span>  <br/> <span data-ttu-id="80a95-423">numru Tal-Passaport</span><span class="sxs-lookup"><span data-stu-id="80a95-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="80a95-424">Niederlande</span><span class="sxs-lookup"><span data-stu-id="80a95-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="80a95-425">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-425">Format</span></span>

<span data-ttu-id="80a95-426">Neun Buchstaben oder Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-427">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-427">Pattern</span></span>

<span data-ttu-id="80a95-428">Neun Buchstaben oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="80a95-429">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-429">Checksum</span></span>

<span data-ttu-id="80a95-430">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="80a95-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-431">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-431">Definition</span></span>

<span data-ttu-id="80a95-432">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-433">Der reguläre Ausdruck `Regex_netherlands_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-434">Ein Schlüsselwort `Keywords_netherlands_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-435">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-435">Keywords</span></span>

<span data-ttu-id="80a95-436">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-436">| |</span></span>
|<span data-ttu-id="80a95-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-438">niederländische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-438">dutch passport number</span></span>  <br/> <span data-ttu-id="80a95-439">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-439">passport number</span></span>  <br/> <span data-ttu-id="80a95-440">niederländische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="80a95-441">Nederlanden paspoort Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="80a95-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="80a95-442">paspoort</span></span>  <br/> <span data-ttu-id="80a95-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="80a95-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="80a95-445">Polen</span><span class="sxs-lookup"><span data-stu-id="80a95-445">Poland</span></span>

<span data-ttu-id="80a95-446">Ausführliche Informationen finden Sie im Abschnitt "Polen-Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="80a95-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="80a95-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="80a95-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="80a95-448">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-448">Format</span></span>

<span data-ttu-id="80a95-449">Ein Buchstabe, gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-450">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-450">Pattern</span></span>

<span data-ttu-id="80a95-451">Ein Buchstabe, gefolgt von sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="80a95-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="80a95-452">Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="80a95-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="80a95-453">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="80a95-454">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-454">Checksum</span></span>

<span data-ttu-id="80a95-455">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-456">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-456">Definition</span></span>

<span data-ttu-id="80a95-457">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-458">Der reguläre Ausdruck `Regex_portugal_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-459">Ein Schlüsselwort `Keywords_portugal_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-460">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-460">Keywords</span></span>

<span data-ttu-id="80a95-461">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-461">| |</span></span>
|<span data-ttu-id="80a95-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-463">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-463">passport number</span></span>  <br/> <span data-ttu-id="80a95-464">portugiesische Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="80a95-465">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-465">passport no</span></span>  <br/> <span data-ttu-id="80a95-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="80a95-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="80a95-467">Rumänien</span><span class="sxs-lookup"><span data-stu-id="80a95-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="80a95-468">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-468">Format</span></span>

<span data-ttu-id="80a95-469">Acht oder neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-470">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-470">Pattern</span></span>

<span data-ttu-id="80a95-471">Acht oder neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="80a95-472">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-472">Checksum</span></span>

<span data-ttu-id="80a95-473">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-474">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-474">Definition</span></span>

<span data-ttu-id="80a95-475">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-476">Der reguläre Ausdruck `Regex_romania_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-477">Ein Schlüsselwort `Keywords_romania_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-478">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-478">Keywords</span></span>

<span data-ttu-id="80a95-479">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-479">| |</span></span>
|<span data-ttu-id="80a95-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-481">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-481">passport number</span></span>  <br/> <span data-ttu-id="80a95-482">rumänische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-482">romanian passport number</span></span>  <br/> <span data-ttu-id="80a95-483">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-483">passport no</span></span>  <br/> <span data-ttu-id="80a95-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="80a95-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="80a95-485">Slowakei</span><span class="sxs-lookup"><span data-stu-id="80a95-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="80a95-486">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-486">Format</span></span>

<span data-ttu-id="80a95-487">Eine Ziffer oder ein Buchstabe, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-488">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-488">Pattern</span></span>

<span data-ttu-id="80a95-489">Eine Ziffer oder ein Buchstabe (ohne Groß-/Kleinschreibung), gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="80a95-490">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-490">Checksum</span></span>

<span data-ttu-id="80a95-491">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-492">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-492">Definition</span></span>

<span data-ttu-id="80a95-493">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-494">Der reguläre Ausdruck `Regex_slovakia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-495">Ein Schlüsselwort `Keywords_slovakia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-496">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-496">Keywords</span></span>

<span data-ttu-id="80a95-497">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-497">| |</span></span>
|<span data-ttu-id="80a95-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-499">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-499">passport number</span></span>  <br/> <span data-ttu-id="80a95-500">Slowakische Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="80a95-501">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-501">passport no</span></span>  <br/> <span data-ttu-id="80a95-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="80a95-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="80a95-503">Slowenien</span><span class="sxs-lookup"><span data-stu-id="80a95-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="80a95-504">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-504">Format</span></span>

<span data-ttu-id="80a95-505">Zwei Buchstaben, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-506">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-506">Pattern</span></span>

<span data-ttu-id="80a95-507">Zwei Buchstaben, gefolgt von sieben Ziffern:</span><span class="sxs-lookup"><span data-stu-id="80a95-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="80a95-508">Der Buchstabe "P"</span><span class="sxs-lookup"><span data-stu-id="80a95-508">The letter "P"</span></span>
    
- <span data-ttu-id="80a95-509">Ein Großbuchstabe</span><span class="sxs-lookup"><span data-stu-id="80a95-509">One uppercase letter</span></span>
    
- <span data-ttu-id="80a95-510">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="80a95-511">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-511">Checksum</span></span>

<span data-ttu-id="80a95-512">Nein</span><span class="sxs-lookup"><span data-stu-id="80a95-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-513">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-513">Definition</span></span>

<span data-ttu-id="80a95-514">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-515">Der reguläre Ausdruck `Regex_slovenia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-516">Ein Schlüsselwort `Keywords_slovenia_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-517">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-517">Keywords</span></span>

<span data-ttu-id="80a95-518">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-518">| |</span></span>
|<span data-ttu-id="80a95-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-520">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-520">passport number</span></span>  <br/> <span data-ttu-id="80a95-521">slowenische Passnummer</span><span class="sxs-lookup"><span data-stu-id="80a95-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="80a95-522">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-522">passport no</span></span>  <br/> <span data-ttu-id="80a95-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="80a95-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="80a95-524">Spanien</span><span class="sxs-lookup"><span data-stu-id="80a95-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="80a95-525">Format</span><span class="sxs-lookup"><span data-stu-id="80a95-525">Format</span></span>

<span data-ttu-id="80a95-526">Eine Kombination aus Buchstaben und Zahlen mit acht oder neun Zeichen ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="80a95-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="80a95-527">Muster</span><span class="sxs-lookup"><span data-stu-id="80a95-527">Pattern</span></span>

<span data-ttu-id="80a95-528">Eine Kombination aus Buchstaben und Zahlen aus acht oder neun Zeichen:</span><span class="sxs-lookup"><span data-stu-id="80a95-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="80a95-529">Zwei Ziffern oder Buchstaben</span><span class="sxs-lookup"><span data-stu-id="80a95-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="80a95-530">Eine Ziffer oder ein Buchstabe (optional)</span><span class="sxs-lookup"><span data-stu-id="80a95-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="80a95-531">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="80a95-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="80a95-532">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="80a95-532">Checksum</span></span>

<span data-ttu-id="80a95-533">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="80a95-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="80a95-534">Definition</span><span class="sxs-lookup"><span data-stu-id="80a95-534">Definition</span></span>

<span data-ttu-id="80a95-535">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="80a95-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="80a95-536">Der reguläre Ausdruck `Regex_spain_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80a95-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="80a95-537">Ein Schlüsselwort `Keywords_spain_eu_passport_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="80a95-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="80a95-538">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80a95-538">Keywords</span></span>

<span data-ttu-id="80a95-539">| |</span><span class="sxs-lookup"><span data-stu-id="80a95-539">| |</span></span>
|<span data-ttu-id="80a95-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="80a95-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="80a95-541">Pass</span><span class="sxs-lookup"><span data-stu-id="80a95-541">passport</span></span>  <br/> <span data-ttu-id="80a95-542">Spanien-Passport</span><span class="sxs-lookup"><span data-stu-id="80a95-542">spain passport</span></span>  <br/> <span data-ttu-id="80a95-543">Passport-Buch</span><span class="sxs-lookup"><span data-stu-id="80a95-543">passport book</span></span>  <br/> <span data-ttu-id="80a95-544">passport number</span><span class="sxs-lookup"><span data-stu-id="80a95-544">passport number</span></span>  <br/> <span data-ttu-id="80a95-545">Passport-Nummer</span><span class="sxs-lookup"><span data-stu-id="80a95-545">passport no</span></span>  <br/> <span data-ttu-id="80a95-546">Libreta Pasaporte</span><span class="sxs-lookup"><span data-stu-id="80a95-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="80a95-547">número Pasaporte</span><span class="sxs-lookup"><span data-stu-id="80a95-547">número pasaporte</span></span>  <br/> <span data-ttu-id="80a95-548">ESPAÑA PASAPORTE</span><span class="sxs-lookup"><span data-stu-id="80a95-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="80a95-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="80a95-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="80a95-550">Schweden</span><span class="sxs-lookup"><span data-stu-id="80a95-550">Sweden</span></span>

<span data-ttu-id="80a95-551">Ausführliche Informationen finden Sie im Abschnitt "schwedische Passport-Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="80a95-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="80a95-552">UK</span><span class="sxs-lookup"><span data-stu-id="80a95-552">UK</span></span>

<span data-ttu-id="80a95-553">Ausführliche Informationen finden Sie im Abschnitt "U.S./U.K.</span><span class="sxs-lookup"><span data-stu-id="80a95-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="80a95-554">Passport-Nummer "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="80a95-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="80a95-555">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="80a95-555">See also</span></span>

[<span data-ttu-id="80a95-556">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="80a95-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

