---
title: EU-Steueridentifikationsnummer
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
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp "EU-Steueridentifikationsnummer" erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: 5467db921bd518eeeab18a36ee2de473f9017358
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41591016"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="52cbf-104">EU-Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-104">EU Tax Identification Number</span></span>

<span data-ttu-id="52cbf-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn Sie den Typ der vertraulichen Informationen für die EU-Steueridentifikationsnummer (TIN) erkennt.</span><span class="sxs-lookup"><span data-stu-id="52cbf-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="52cbf-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="52cbf-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="52cbf-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="52cbf-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-108">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-108">Format</span></span>

<span data-ttu-id="52cbf-109">Neun Ziffern mit optionalem Bindestrich und Schrägstrich</span><span class="sxs-lookup"><span data-stu-id="52cbf-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-110">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-110">Pattern</span></span>

<span data-ttu-id="52cbf-111">Neun Ziffern mit optionalem Bindestrich und Schrägstrich:</span><span class="sxs-lookup"><span data-stu-id="52cbf-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="52cbf-112">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-112">Two digits</span></span> 
    
- <span data-ttu-id="52cbf-113">Ein Bindestrich (optional)</span><span class="sxs-lookup"><span data-stu-id="52cbf-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="52cbf-114">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-114">Three digits</span></span>
    
- <span data-ttu-id="52cbf-115">Ein Schrägstrich (optional)</span><span class="sxs-lookup"><span data-stu-id="52cbf-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="52cbf-116">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-117">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-117">Checksum</span></span>

<span data-ttu-id="52cbf-118">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-119">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-119">Definition</span></span>

<span data-ttu-id="52cbf-120">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-121">Die- `Func_austria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-122">Ein Schlüsselwort `Keywords_austria_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-123">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-124">Die- `Func_austria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-125">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="52cbf-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-127">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-127">tax number</span></span>
  
<span data-ttu-id="52cbf-128">number</span><span class="sxs-lookup"><span data-stu-id="52cbf-128">number</span></span>
  
<span data-ttu-id="52cbf-129">Steuerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-129">tax registration number</span></span>
  
<span data-ttu-id="52cbf-130">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-130">tax id</span></span>
  
<span data-ttu-id="52cbf-131">St.Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-131">st.nr.</span></span>
  
<span data-ttu-id="52cbf-132">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="52cbf-133">Belgien</span><span class="sxs-lookup"><span data-stu-id="52cbf-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-134">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-134">Format</span></span>

<span data-ttu-id="52cbf-135">11 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-136">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-136">Pattern</span></span>

<span data-ttu-id="52cbf-137">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="52cbf-137">11 digits:</span></span>
  
- <span data-ttu-id="52cbf-138">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-138">Two digits</span></span>
    
- <span data-ttu-id="52cbf-139">A "0" oder "1"</span><span class="sxs-lookup"><span data-stu-id="52cbf-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="52cbf-140">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="52cbf-140">One digit</span></span>
    
- <span data-ttu-id="52cbf-141">A "0" oder "1" oder "2" oder "3"</span><span class="sxs-lookup"><span data-stu-id="52cbf-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="52cbf-142">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-143">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-143">Checksum</span></span>

<span data-ttu-id="52cbf-144">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="52cbf-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-145">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-145">Definition</span></span>

<span data-ttu-id="52cbf-146">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-147">Der reguläre Ausdruck `Regex_belgium_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-148">Ein Schlüsselwort `Keywords_belgium_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-149">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="52cbf-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-151">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-151">tax number</span></span>
  
<span data-ttu-id="52cbf-152">nationale Registrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-152">national registration number</span></span>
  
<span data-ttu-id="52cbf-153">Steuerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-153">tax registration number</span></span>
  
<span data-ttu-id="52cbf-154">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-154">tax id</span></span>
  
<span data-ttu-id="52cbf-155">NIF</span><span class="sxs-lookup"><span data-stu-id="52cbf-155">nif</span></span>
  
<span data-ttu-id="52cbf-156">NIF #</span><span class="sxs-lookup"><span data-stu-id="52cbf-156">nif#</span></span>
  
<span data-ttu-id="52cbf-157">Numéro de Registre National</span><span class="sxs-lookup"><span data-stu-id="52cbf-157">numéro de registre national</span></span>
  
<span data-ttu-id="52cbf-158">Numéro d'identification Fiscale</span><span class="sxs-lookup"><span data-stu-id="52cbf-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="52cbf-159">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="52cbf-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-160">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-160">Format</span></span>

<span data-ttu-id="52cbf-161">Zehn Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-162">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-162">Pattern</span></span>

<span data-ttu-id="52cbf-163">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="52cbf-164">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-164">Checksum</span></span>

<span data-ttu-id="52cbf-165">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-166">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-166">Definition</span></span>

<span data-ttu-id="52cbf-167">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-168">Die- `Func_bulgaria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-169">Ein Schlüsselwort `Keywords_bulgaria_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-170">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-171">Die- `Func_bulgaria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-172">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="52cbf-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-174">BUCN</span><span class="sxs-lookup"><span data-stu-id="52cbf-174">bucn</span></span>
  
<span data-ttu-id="52cbf-175">einheitliche Zivil Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-175">uniform civil number</span></span>
  
<span data-ttu-id="52cbf-176">BUCN #</span><span class="sxs-lookup"><span data-stu-id="52cbf-176">bucn#</span></span>
  
<span data-ttu-id="52cbf-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="52cbf-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="52cbf-178">Uniform Civil ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-178">uniform civil id</span></span>
  
<span data-ttu-id="52cbf-179">Uniform Civil Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-179">uniform civil no</span></span>
  
<span data-ttu-id="52cbf-180">EGN</span><span class="sxs-lookup"><span data-stu-id="52cbf-180">egn</span></span>
  
<span data-ttu-id="52cbf-181">Bulgarische Uniform Civil Number</span><span class="sxs-lookup"><span data-stu-id="52cbf-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="52cbf-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-182">uniformcivilno#</span></span>
  
<span data-ttu-id="52cbf-183">EGN #</span><span class="sxs-lookup"><span data-stu-id="52cbf-183">egn#</span></span>
  
<span data-ttu-id="52cbf-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="52cbf-184">униформ граждански номер</span></span>
  
<span data-ttu-id="52cbf-185">униформ-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-185">униформ id</span></span>
  
<span data-ttu-id="52cbf-186">униформ-граждански-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-186">униформ граждански id</span></span>
  
<span data-ttu-id="52cbf-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="52cbf-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="52cbf-188">Kroatien</span><span class="sxs-lookup"><span data-stu-id="52cbf-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-189">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-189">Format</span></span>

<span data-ttu-id="52cbf-190">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-191">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-191">Pattern</span></span>

<span data-ttu-id="52cbf-192">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="52cbf-192">11 digits:</span></span>
  
- <span data-ttu-id="52cbf-193">Zehn Ziffern, nach dem Zufallsprinzip ausgewählt</span><span class="sxs-lookup"><span data-stu-id="52cbf-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="52cbf-194">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="52cbf-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-195">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-195">Checksum</span></span>

<span data-ttu-id="52cbf-196">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-197">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-197">Definition</span></span>

<span data-ttu-id="52cbf-198">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-199">Die- `Func_croatia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-200">Ein Schlüsselwort `Keywords_croatia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-201">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-202">Die- `Func_croatia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-203">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="52cbf-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-205">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-205">tax number</span></span>
  
<span data-ttu-id="52cbf-206">Steuer</span><span class="sxs-lookup"><span data-stu-id="52cbf-206">tax</span></span>
  
<span data-ttu-id="52cbf-207">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-207">tax id</span></span>
  
<span data-ttu-id="52cbf-208">oid</span><span class="sxs-lookup"><span data-stu-id="52cbf-208">oid</span></span>
  
<span data-ttu-id="52cbf-209">OID #</span><span class="sxs-lookup"><span data-stu-id="52cbf-209">oid#</span></span>
  
<span data-ttu-id="52cbf-210">porezni Broj</span><span class="sxs-lookup"><span data-stu-id="52cbf-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="52cbf-211">Zypern</span><span class="sxs-lookup"><span data-stu-id="52cbf-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-212">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-212">Format</span></span>

<span data-ttu-id="52cbf-213">Acht Ziffern und ein Buchstabe im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-214">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-214">Pattern</span></span>

<span data-ttu-id="52cbf-215">Acht Ziffern und ein Buchstabe:</span><span class="sxs-lookup"><span data-stu-id="52cbf-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="52cbf-216">A "0"</span><span class="sxs-lookup"><span data-stu-id="52cbf-216">A "0"</span></span> 
    
- <span data-ttu-id="52cbf-217">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="52cbf-217">Seven digits</span></span>
    
- <span data-ttu-id="52cbf-218">Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="52cbf-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-219">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-219">Checksum</span></span>

<span data-ttu-id="52cbf-220">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="52cbf-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-221">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-221">Definition</span></span>

<span data-ttu-id="52cbf-222">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-223">Die- `Func_cyprus_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-224">Ein Schlüsselwort `Keywords_cyprus_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-225">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-226">Die- `Func_cyprus_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-227">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="52cbf-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-229">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-229">tax number</span></span>
  
<span data-ttu-id="52cbf-230">Steuer</span><span class="sxs-lookup"><span data-stu-id="52cbf-230">tax</span></span>
  
<span data-ttu-id="52cbf-231">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-231">tax id</span></span>
  
<span data-ttu-id="52cbf-232">Steuer Identifikationscode</span><span class="sxs-lookup"><span data-stu-id="52cbf-232">tax identification code</span></span>
  
<span data-ttu-id="52cbf-233">TIC</span><span class="sxs-lookup"><span data-stu-id="52cbf-233">tic</span></span>
  
<span data-ttu-id="52cbf-234">TIC #</span><span class="sxs-lookup"><span data-stu-id="52cbf-234">tic#</span></span>
  
<span data-ttu-id="52cbf-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="52cbf-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="52cbf-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="52cbf-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="52cbf-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="52cbf-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="52cbf-238">Tschechien</span><span class="sxs-lookup"><span data-stu-id="52cbf-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-239">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-239">Format</span></span>

<span data-ttu-id="52cbf-240">Neun oder zehn Ziffern mit einem optionalen Backslash</span><span class="sxs-lookup"><span data-stu-id="52cbf-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-241">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-241">Pattern</span></span>

<span data-ttu-id="52cbf-242">Neun oder zehn Ziffern mit einem optionalen backslashl:</span><span class="sxs-lookup"><span data-stu-id="52cbf-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="52cbf-243">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-243">Six digits</span></span> 
    
- <span data-ttu-id="52cbf-244">Ein Backslash (optional)</span><span class="sxs-lookup"><span data-stu-id="52cbf-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="52cbf-245">Drei oder vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-246">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-246">Checksum</span></span>

<span data-ttu-id="52cbf-247">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="52cbf-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-248">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-248">Definition</span></span>

<span data-ttu-id="52cbf-249">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-250">Der reguläre Ausdruck `Regex_czech_republic_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-251">Ein Schlüsselwort `Keywords_czech_republic_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-252">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="52cbf-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-254">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-254">tax number</span></span>
  
<span data-ttu-id="52cbf-255">Steuer</span><span class="sxs-lookup"><span data-stu-id="52cbf-255">tax</span></span>
  
<span data-ttu-id="52cbf-256">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-256">tax id</span></span>
  
<span data-ttu-id="52cbf-257">persönliche Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-257">personal number</span></span>
  
<span data-ttu-id="52cbf-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="52cbf-258">daňové číslo</span></span>
  
<span data-ttu-id="52cbf-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="52cbf-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="52cbf-260">Dänemark</span><span class="sxs-lookup"><span data-stu-id="52cbf-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-261">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-261">Format</span></span>

<span data-ttu-id="52cbf-262">Zehn Ziffern mit einem Bindestrich</span><span class="sxs-lookup"><span data-stu-id="52cbf-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-263">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-263">Pattern</span></span>

<span data-ttu-id="52cbf-264">Zehn Ziffern mit einem Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="52cbf-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="52cbf-265">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="52cbf-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="52cbf-266">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="52cbf-266">A hyphen</span></span>
    
- <span data-ttu-id="52cbf-267">Vier Ziffern, die einer Sequenznummer entsprechen, wobei die erste Ziffer dem Jahrhundert der Geburt entspricht und die letzte Ziffer dem Geschlecht der Person entspricht (ungerade für männliche und sogar für weiblich)</span><span class="sxs-lookup"><span data-stu-id="52cbf-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-268">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-268">Checksum</span></span>

<span data-ttu-id="52cbf-269">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-270">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-270">Definition</span></span>

<span data-ttu-id="52cbf-271">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-272">Die- `Func_denmark_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-273">Ein Schlüsselwort `Keywords_denmark_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-274">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-275">Die- `Func_denmark_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-276">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="52cbf-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-278">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-278">tax number</span></span>
  
<span data-ttu-id="52cbf-279">Steuer</span><span class="sxs-lookup"><span data-stu-id="52cbf-279">tax</span></span>
  
<span data-ttu-id="52cbf-280">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-280">tax id</span></span>
  
<span data-ttu-id="52cbf-281">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-281">cpr number</span></span>
  
<span data-ttu-id="52cbf-282">CPR #</span><span class="sxs-lookup"><span data-stu-id="52cbf-282">cpr#</span></span>
  
<span data-ttu-id="52cbf-283">Skate Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-283">skat nummer</span></span>
  
<span data-ttu-id="52cbf-284">Skat-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="52cbf-285">Estland</span><span class="sxs-lookup"><span data-stu-id="52cbf-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-286">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-286">Format</span></span>

<span data-ttu-id="52cbf-287">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-288">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-288">Pattern</span></span>

<span data-ttu-id="52cbf-289">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="52cbf-289">11 digits:</span></span>
  
-  <span data-ttu-id="52cbf-290">Eine Ziffer, die dem Geschlecht und dem Jahrhundert der Geburt entspricht, wobei eine ungerade Zahl männlich ist und die gerade Zahl weiblich wie folgt angibt: 1, 2 für das 19. Jahrhundert; 3,4 für das 20. Jahrhundert; und 5, 6 für das 21. Jahrhundert</span><span class="sxs-lookup"><span data-stu-id="52cbf-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="52cbf-291">Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)</span><span class="sxs-lookup"><span data-stu-id="52cbf-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="52cbf-292">Drei Ziffern, die einer Seriennummer entsprechen, die Personen trennt, die am gleichen Datum geboren wurden</span><span class="sxs-lookup"><span data-stu-id="52cbf-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="52cbf-293">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="52cbf-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-294">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-294">Checksum</span></span>

<span data-ttu-id="52cbf-295">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-296">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-296">Definition</span></span>

<span data-ttu-id="52cbf-297">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-298">Die- `Func_estonia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-299">Ein Schlüsselwort `Keywords_estonia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-300">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-301">Die- `Func_estonia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-302">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="52cbf-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-304">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-304">tax number</span></span>
  
<span data-ttu-id="52cbf-305">Steuer</span><span class="sxs-lookup"><span data-stu-id="52cbf-305">tax</span></span>
  
<span data-ttu-id="52cbf-306">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-306">tax id</span></span>
  
<span data-ttu-id="52cbf-307">persönlicher Code</span><span class="sxs-lookup"><span data-stu-id="52cbf-307">personal code</span></span>
  
<span data-ttu-id="52cbf-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="52cbf-308">maksunumber</span></span>
  
<span data-ttu-id="52cbf-309">maksu-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-309">maksu id</span></span>
  
<span data-ttu-id="52cbf-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="52cbf-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="52cbf-311">Finnland</span><span class="sxs-lookup"><span data-stu-id="52cbf-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-312">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-312">Format</span></span>

<span data-ttu-id="52cbf-313">Eine Kombination aus 11 Zeichen aus Ziffern, Buchstaben und Plus-und Minuszeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-314">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-314">Pattern</span></span>

<span data-ttu-id="52cbf-315">Eine Kombination aus 11 Zeichen aus Ziffern, Buchstaben und Plus-und Minuszeichen:</span><span class="sxs-lookup"><span data-stu-id="52cbf-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="52cbf-316">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-316">Six digits</span></span>
    
- <span data-ttu-id="52cbf-317">Eine der folgenden Optionen: ein Pluszeichen, ein Minuszeichen oder der Buchstabe "a" (Groß-/Kleinschreibung nicht beachtet), wobei das Pluszeichen zwischen 1800-1899 geboren wird, das Minuszeichen zwischen 1900-1999 und "a" geboren ist 2000 und nach</span><span class="sxs-lookup"><span data-stu-id="52cbf-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="52cbf-318">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-318">Three digits</span></span>
    
- <span data-ttu-id="52cbf-319">Ein Buchstabe oder eine Zahl</span><span class="sxs-lookup"><span data-stu-id="52cbf-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-320">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-320">Checksum</span></span>

<span data-ttu-id="52cbf-321">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-322">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-322">Definition</span></span>

<span data-ttu-id="52cbf-323">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-324">Die- `Func_finland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-325">Ein Schlüsselwort `Keywords_finland_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-326">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-327">Die- `Func_finland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-328">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="52cbf-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-330">identification number</span><span class="sxs-lookup"><span data-stu-id="52cbf-330">identification number</span></span>
  
<span data-ttu-id="52cbf-331">persönliche ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-331">personal id</span></span>
  
<span data-ttu-id="52cbf-332">Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-332">identity number</span></span>
  
<span data-ttu-id="52cbf-333">Finnische Nationale ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-333">finnish national id number</span></span>
  
<span data-ttu-id="52cbf-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="52cbf-334">personalidnumber#</span></span>
  
<span data-ttu-id="52cbf-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="52cbf-335">national identification number</span></span>
  
<span data-ttu-id="52cbf-336">ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-336">id number</span></span>
  
<span data-ttu-id="52cbf-337">nationale ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-337">national id no.</span></span>
  
<span data-ttu-id="52cbf-338">nationale ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-338">national id number</span></span>
  
<span data-ttu-id="52cbf-339">ID Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-339">id no</span></span>
  
<span data-ttu-id="52cbf-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="52cbf-340">tunnistenumero</span></span>
  
<span data-ttu-id="52cbf-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="52cbf-341">henkilötunnus</span></span>
  
<span data-ttu-id="52cbf-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="52cbf-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="52cbf-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="52cbf-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="52cbf-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="52cbf-344">identiteetti numero</span></span>
  
<span data-ttu-id="52cbf-345">Suomen der Kok henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="52cbf-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="52cbf-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="52cbf-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="52cbf-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="52cbf-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="52cbf-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="52cbf-348">tunnusnumero</span></span>
  
<span data-ttu-id="52cbf-349">der Kok tunnus numero</span><span class="sxs-lookup"><span data-stu-id="52cbf-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="52cbf-350">Frankreich</span><span class="sxs-lookup"><span data-stu-id="52cbf-350">France</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-351">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-351">Format</span></span>

<span data-ttu-id="52cbf-352">13 Ziffern für einzelne Personen und neun Ziffern für Entitäten</span><span class="sxs-lookup"><span data-stu-id="52cbf-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-353">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-353">Pattern</span></span>

<span data-ttu-id="52cbf-354">13 Ziffern für einzelne Personen:</span><span class="sxs-lookup"><span data-stu-id="52cbf-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="52cbf-355">Eine Ziffer, die 0, 1, 2 oder 3 sein muss</span><span class="sxs-lookup"><span data-stu-id="52cbf-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="52cbf-356">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-356">12 digits</span></span>
    
<span data-ttu-id="52cbf-357">Neun Ziffern für Entitäten</span><span class="sxs-lookup"><span data-stu-id="52cbf-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="52cbf-358">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-358">Checksum</span></span>

<span data-ttu-id="52cbf-359">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="52cbf-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-360">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-360">Definition</span></span>

<span data-ttu-id="52cbf-361">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-362">Die- `Func_france_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-363">Ein Schlüsselwort `Keywords_france_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-364">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-365">Die- `Func_france_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-366">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="52cbf-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-368">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-368">tax identification number</span></span>
  
<span data-ttu-id="52cbf-369">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-369">tax number</span></span>
  
<span data-ttu-id="52cbf-370">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-370">tax id</span></span>
  
<span data-ttu-id="52cbf-371">Numéro d'identification Fiscale</span><span class="sxs-lookup"><span data-stu-id="52cbf-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="52cbf-372">Deutschland</span><span class="sxs-lookup"><span data-stu-id="52cbf-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-373">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-373">Format</span></span>

<span data-ttu-id="52cbf-374">11 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-375">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-375">Pattern</span></span>

<span data-ttu-id="52cbf-376">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="52cbf-376">11 digits :</span></span>
  
-  <span data-ttu-id="52cbf-377">Zehn Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-377">Ten digits</span></span> 
    
- <span data-ttu-id="52cbf-378">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="52cbf-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-379">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-379">Checksum</span></span>

<span data-ttu-id="52cbf-380">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-381">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-381">Definition</span></span>

<span data-ttu-id="52cbf-382">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-383">Die- `Func_germany_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-384">Ein Schlüsselwort `Keywords_germany_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-385">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-386">Die- `Func_germany_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-387">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="52cbf-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-389">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-389">tax number</span></span>
  
<span data-ttu-id="52cbf-390">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-390">tax no.</span></span>
  
<span data-ttu-id="52cbf-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-391">taxno#</span></span>
  
<span data-ttu-id="52cbf-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="52cbf-392">taxnumber#</span></span>
  
<span data-ttu-id="52cbf-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="52cbf-393">taxnumber</span></span>
  
<span data-ttu-id="52cbf-394">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-394">tax id</span></span>
  
<span data-ttu-id="52cbf-395">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="52cbf-395">taxid#</span></span>
  
<span data-ttu-id="52cbf-396">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-396">tax identification number</span></span>
  
<span data-ttu-id="52cbf-397">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-397">tax identification no.</span></span>
  
<span data-ttu-id="52cbf-398">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-398">steuernummer</span></span>
  
<span data-ttu-id="52cbf-399">Ingo-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-399">steuer id</span></span>
  
<span data-ttu-id="52cbf-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="52cbf-401">Griechenland</span><span class="sxs-lookup"><span data-stu-id="52cbf-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-402">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-402">Format</span></span>

<span data-ttu-id="52cbf-403">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-404">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-404">Pattern</span></span>

<span data-ttu-id="52cbf-405">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="52cbf-406">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-406">Checksum</span></span>

<span data-ttu-id="52cbf-407">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="52cbf-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-408">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-408">Definition</span></span>

<span data-ttu-id="52cbf-409">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-410">Der reguläre Ausdruck `Regex_greece_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-411">Ein Schlüsselwort `Keywords_greece_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-412">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="52cbf-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-414">AFM</span><span class="sxs-lookup"><span data-stu-id="52cbf-414">afm</span></span>
  
<span data-ttu-id="52cbf-415">Zinn</span><span class="sxs-lookup"><span data-stu-id="52cbf-415">tin</span></span>
  
<span data-ttu-id="52cbf-416">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-416">tax id no.</span></span>
  
<span data-ttu-id="52cbf-417">Steuernummer Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-417">tax id no</span></span>
  
<span data-ttu-id="52cbf-418">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-418">tax identification number</span></span>
  
<span data-ttu-id="52cbf-419">Steuerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-419">tax registry number</span></span>
  
<span data-ttu-id="52cbf-420">Steuerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-420">tax registry no.</span></span>
  
<span data-ttu-id="52cbf-421">AFM #</span><span class="sxs-lookup"><span data-stu-id="52cbf-421">afm#</span></span>
  
<span data-ttu-id="52cbf-422">Zinn #</span><span class="sxs-lookup"><span data-stu-id="52cbf-422">tin#</span></span>
  
<span data-ttu-id="52cbf-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-423">taxidno#</span></span>
  
<span data-ttu-id="52cbf-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-424">taxregistryno#</span></span>
  
<span data-ttu-id="52cbf-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="52cbf-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="52cbf-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="52cbf-426">aφμ</span></span>
  
<span data-ttu-id="52cbf-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="52cbf-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="52cbf-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="52cbf-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="52cbf-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="52cbf-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="52cbf-430">Ungarn</span><span class="sxs-lookup"><span data-stu-id="52cbf-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-431">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-431">Format</span></span>

<span data-ttu-id="52cbf-432">Zehn Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-433">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-433">Pattern</span></span>

<span data-ttu-id="52cbf-434">Zehn Ziffern:</span><span class="sxs-lookup"><span data-stu-id="52cbf-434">Ten digits:</span></span>
  
-  <span data-ttu-id="52cbf-435">Eine Ziffer, die "8" sein muss</span><span class="sxs-lookup"><span data-stu-id="52cbf-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="52cbf-436">Fünf Ziffern, die der Anzahl von Tagen zwischen dem Datum 01/01/1867 und dem Geburtsdatum der einzelnen Personen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="52cbf-437">Drei Ziffern, die der durch Zufall generierten Zahl entsprechen, um Personen zu unterscheiden, die am selben Tag geboren wurden</span><span class="sxs-lookup"><span data-stu-id="52cbf-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="52cbf-438">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="52cbf-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-439">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-439">Checksum</span></span>

<span data-ttu-id="52cbf-440">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-441">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-441">Definition</span></span>

<span data-ttu-id="52cbf-442">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-443">Die- `Func_hungary_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-444">Ein Schlüsselwort `Keywords_hungary_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-445">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-446">Die- `Func_hungary_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-447">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="52cbf-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-449">ungarische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="52cbf-450">Ungarisch Zinn</span><span class="sxs-lookup"><span data-stu-id="52cbf-450">hungarian tin</span></span>
  
<span data-ttu-id="52cbf-451">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-451">tax id number</span></span>
  
<span data-ttu-id="52cbf-452">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-452">vat number</span></span>
  
<span data-ttu-id="52cbf-453">Steuerbehörde Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-453">tax authority no</span></span>
  
<span data-ttu-id="52cbf-454">USt-ID-Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-454">tax id tax identity number</span></span>
  
<span data-ttu-id="52cbf-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="52cbf-455">taxidnumber#</span></span>
  
<span data-ttu-id="52cbf-456">Zinn #</span><span class="sxs-lookup"><span data-stu-id="52cbf-456">tin#</span></span>
  
<span data-ttu-id="52cbf-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="52cbf-457">hungatiantin#</span></span>
  
<span data-ttu-id="52cbf-458">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-458">tax identification no</span></span>
  
<span data-ttu-id="52cbf-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-459">taxidno#</span></span>
  
<span data-ttu-id="52cbf-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="52cbf-460">adóazonosító szám</span></span>
  
<span data-ttu-id="52cbf-461">adószám</span><span class="sxs-lookup"><span data-stu-id="52cbf-461">adószám</span></span>
  
<span data-ttu-id="52cbf-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="52cbf-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="52cbf-463">Irland</span><span class="sxs-lookup"><span data-stu-id="52cbf-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-464">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-464">Format</span></span>

<span data-ttu-id="52cbf-465">Sieben Ziffern, gefolgt von einem Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-466">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-466">Pattern</span></span>

<span data-ttu-id="52cbf-467">Sieben Ziffern, gefolgt von einem Buchstaben:</span><span class="sxs-lookup"><span data-stu-id="52cbf-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="52cbf-468">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="52cbf-468">Seven digits</span></span> 
    
- <span data-ttu-id="52cbf-469">Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="52cbf-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-470">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-470">Checksum</span></span>

<span data-ttu-id="52cbf-471">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="52cbf-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-472">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-472">Definition</span></span>

<span data-ttu-id="52cbf-473">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-474">Die- `Func_ireland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-475">Ein Schlüsselwort `Keywords_ireland_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-476">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-477">Die- `Func_ireland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-478">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="52cbf-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-480">öffentlicher Dienst Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-480">public service no</span></span>
  
<span data-ttu-id="52cbf-481">persönlicher öffentlicher Dienst Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-481">personal public service no</span></span>
  
<span data-ttu-id="52cbf-482">PPS Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-482">pps no</span></span>
  
<span data-ttu-id="52cbf-483">persönlicher Dienst Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-483">personal service no</span></span>
  
<span data-ttu-id="52cbf-484">PPS-Dienst Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-484">pps service no</span></span>
  
<span data-ttu-id="52cbf-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-485">ppsno#</span></span>
  
<span data-ttu-id="52cbf-486">irische PPS Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-486">irish pps no</span></span>
  
<span data-ttu-id="52cbf-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-487">publicserviceno#</span></span>
  
<span data-ttu-id="52cbf-488">persönliche öffentliche Dienstnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-488">personal public service number</span></span>
  
<span data-ttu-id="52cbf-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="52cbf-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="52cbf-490">PPS-uimh</span><span class="sxs-lookup"><span data-stu-id="52cbf-490">pps uimh</span></span>
  
<span data-ttu-id="52cbf-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="52cbf-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="52cbf-492">Italien</span><span class="sxs-lookup"><span data-stu-id="52cbf-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-493">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-493">Format</span></span>

<span data-ttu-id="52cbf-494">16 Buchstaben und Ziffern im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-495">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-495">Pattern</span></span>

<span data-ttu-id="52cbf-496">16 Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="52cbf-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="52cbf-497">Drei Buchstaben, die den ersten drei Konsonanten im Familiennamen entsprechen</span><span class="sxs-lookup"><span data-stu-id="52cbf-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="52cbf-498">Drei Buchstaben, die den ersten, dritten und vierten Konsonanten im Vornamen entsprechen</span><span class="sxs-lookup"><span data-stu-id="52cbf-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="52cbf-499">Zwei Ziffern, die den letzten Ziffern des Geburtsjahres entsprechen</span><span class="sxs-lookup"><span data-stu-id="52cbf-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="52cbf-500">Eine Ziffer, die dem Monat der Geburt entspricht – Buchstaben werden in alphabetischer Reihenfolge verwendet, aber nur die Buchstaben a bis E, H, L, M, P, R bis T werden verwendet (der Januar ist also a und Oktober ist r).</span><span class="sxs-lookup"><span data-stu-id="52cbf-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="52cbf-501">Zwei Ziffern, die dem Tag des Geburtsmonats entsprechen, in dem 40 dem Tag der Geburt hinzugefügt wird, damit weibliche Personen von Männern unterscheiden können</span><span class="sxs-lookup"><span data-stu-id="52cbf-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="52cbf-502">Vier Ziffern, die einer Ortskennzahl entsprechen, die für die Gemeinde spezifisch ist, in der die Person geboren wurde – landesweite Codes werden für fremde Länder verwendet</span><span class="sxs-lookup"><span data-stu-id="52cbf-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="52cbf-503">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="52cbf-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-504">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-504">Checksum</span></span>

<span data-ttu-id="52cbf-505">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-506">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-506">Definition</span></span>

<span data-ttu-id="52cbf-507">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-508">Die- `Func_italy_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-509">Ein Schlüsselwort `Keywords_italy_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-510">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-511">Die- `Func_italy_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-512">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="52cbf-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-514">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-514">tax number</span></span>
  
<span data-ttu-id="52cbf-515">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-515">tax no.</span></span>
  
<span data-ttu-id="52cbf-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-516">taxno#</span></span>
  
<span data-ttu-id="52cbf-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="52cbf-517">taxnumber#</span></span>
  
<span data-ttu-id="52cbf-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="52cbf-518">taxnumber</span></span>
  
<span data-ttu-id="52cbf-519">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-519">tax id</span></span>
  
<span data-ttu-id="52cbf-520">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="52cbf-520">taxid#</span></span>
  
<span data-ttu-id="52cbf-521">Geschäftscode</span><span class="sxs-lookup"><span data-stu-id="52cbf-521">fiscal code</span></span>
  
<span data-ttu-id="52cbf-522">Geschäftsjahr</span><span class="sxs-lookup"><span data-stu-id="52cbf-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="52cbf-523">Lettland</span><span class="sxs-lookup"><span data-stu-id="52cbf-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-524">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-524">Format</span></span>

<span data-ttu-id="52cbf-525">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-526">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-526">Pattern</span></span>

<span data-ttu-id="52cbf-527">11 Ziffern im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="52cbf-528">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="52cbf-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="52cbf-529">Eine Ziffer, die dem Jahrhundert der Geburt entspricht, wobei "0" dem 19. Jahrhundert entspricht, "1" entspricht dem 20. Jahrhundert, und "2" entspricht dem 21. Jahrhundert</span><span class="sxs-lookup"><span data-stu-id="52cbf-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="52cbf-530">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-531">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-531">Checksum</span></span>

<span data-ttu-id="52cbf-532">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-533">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-533">Definition</span></span>

<span data-ttu-id="52cbf-534">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-535">Die- `Func_latvia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-536">Ein Schlüsselwort `Keywords_latvia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-537">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-538">Die- `Func_latvia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-539">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="52cbf-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-541">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-541">tax number</span></span>
  
<span data-ttu-id="52cbf-542">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-542">tax no.</span></span>
  
<span data-ttu-id="52cbf-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-543">taxno#</span></span>
  
<span data-ttu-id="52cbf-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="52cbf-544">taxnumber#</span></span>
  
<span data-ttu-id="52cbf-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="52cbf-545">taxnumber</span></span>
  
<span data-ttu-id="52cbf-546">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-546">tax id</span></span>
  
<span data-ttu-id="52cbf-547">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="52cbf-547">taxid#</span></span>
  
<span data-ttu-id="52cbf-548">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-548">tax identification number</span></span>
  
<span data-ttu-id="52cbf-549">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-549">tax identification no.</span></span>
  
<span data-ttu-id="52cbf-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="52cbf-550">nodokļa numurs</span></span>
  
<span data-ttu-id="52cbf-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="52cbf-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="52cbf-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="52cbf-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="52cbf-553">Litauen</span><span class="sxs-lookup"><span data-stu-id="52cbf-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-554">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-554">Format</span></span>

<span data-ttu-id="52cbf-555">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-556">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-556">Pattern</span></span>

<span data-ttu-id="52cbf-557">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="52cbf-558">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-558">Checksum</span></span>

<span data-ttu-id="52cbf-559">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="52cbf-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-560">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-560">Definition</span></span>

<span data-ttu-id="52cbf-561">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-562">Die- `Func_lithuania_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-563">Ein Schlüsselwort `Keywords_lithuania_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-564">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-565">Die- `Func_lithuania_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-566">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="52cbf-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-568">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-568">tax number</span></span>
  
<span data-ttu-id="52cbf-569">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-569">tax no.</span></span>
  
<span data-ttu-id="52cbf-570">Steuernummer #</span><span class="sxs-lookup"><span data-stu-id="52cbf-570">tax no#</span></span>
  
<span data-ttu-id="52cbf-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="52cbf-571">taxnumber#</span></span>
  
<span data-ttu-id="52cbf-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="52cbf-572">taxnumber</span></span>
  
<span data-ttu-id="52cbf-573">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-573">tax id</span></span>
  
<span data-ttu-id="52cbf-574">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="52cbf-574">taxid#</span></span>
  
<span data-ttu-id="52cbf-575">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-575">tax identification number</span></span>
  
<span data-ttu-id="52cbf-576">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-576">tax identification no.</span></span>
  
<span data-ttu-id="52cbf-577">mokesčių-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-577">mokesčių id</span></span>
  
<span data-ttu-id="52cbf-578">mokesčių Numeris</span><span class="sxs-lookup"><span data-stu-id="52cbf-578">mokesčių numeris</span></span>
  
<span data-ttu-id="52cbf-579">mokesčių identifikavimas Numeris</span><span class="sxs-lookup"><span data-stu-id="52cbf-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="52cbf-580">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="52cbf-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-581">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-581">Format</span></span>

<span data-ttu-id="52cbf-582">13 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-583">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-583">Pattern</span></span>

<span data-ttu-id="52cbf-584">13 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="52cbf-584">13 digits:</span></span>
  
-  <span data-ttu-id="52cbf-585">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-585">11 digits</span></span> 
    
- <span data-ttu-id="52cbf-586">Zwei Prüfziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-587">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-587">Checksum</span></span>

<span data-ttu-id="52cbf-588">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-589">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-589">Definition</span></span>

<span data-ttu-id="52cbf-590">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-591">Die- `Func_luxemburg_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-592">Ein Schlüsselwort `Keywords_luxemburg_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-593">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-594">Die- `Func_luxemburg_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-595">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="52cbf-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-597">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-597">tax number</span></span>
  
<span data-ttu-id="52cbf-598">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-598">tax no.</span></span>
  
<span data-ttu-id="52cbf-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-599">taxno#</span></span>
  
<span data-ttu-id="52cbf-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="52cbf-600">taxnumber#</span></span>
  
<span data-ttu-id="52cbf-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="52cbf-601">taxnumber</span></span>
  
<span data-ttu-id="52cbf-602">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-602">tax id</span></span>
  
<span data-ttu-id="52cbf-603">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="52cbf-603">taxid#</span></span>
  
<span data-ttu-id="52cbf-604">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-604">tax identification number</span></span>
  
<span data-ttu-id="52cbf-605">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-605">tax identification no.</span></span>
  
<span data-ttu-id="52cbf-606">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-606">steuernummer</span></span>
  
<span data-ttu-id="52cbf-607">Ingo-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-607">steuer id</span></span>
  
<span data-ttu-id="52cbf-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="52cbf-609">Malta</span><span class="sxs-lookup"><span data-stu-id="52cbf-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-610">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-610">Format</span></span>

<span data-ttu-id="52cbf-611">Für maltesische Staatsangehörige: 7 Ziffern und ein Buchstabe im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="52cbf-612">Nicht-maltesische Staatsangehörige und maltesische Entitäten: 9 Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-613">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-613">Pattern</span></span>

<span data-ttu-id="52cbf-614">Maltesische Staatsangehörige: 7 Ziffern und ein Buchstaben</span><span class="sxs-lookup"><span data-stu-id="52cbf-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="52cbf-615">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="52cbf-615">Seven digits</span></span> 
    
- <span data-ttu-id="52cbf-616">Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="52cbf-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="52cbf-617">Nicht-maltesische Staatsangehörige und maltesische Entitäten: 9 Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="52cbf-618">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="52cbf-619">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-619">Checksum</span></span>

<span data-ttu-id="52cbf-620">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="52cbf-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-621">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-621">Definition</span></span>

<span data-ttu-id="52cbf-622">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-623">Die- `Func_malta_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-624">Ein Schlüsselwort `Keywords_malta_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-625">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-626">Die- `Func_malta_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-627">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="52cbf-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-629">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-629">tax number</span></span>
  
<span data-ttu-id="52cbf-630">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-630">tax no.</span></span>
  
<span data-ttu-id="52cbf-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-631">taxno#</span></span>
  
<span data-ttu-id="52cbf-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="52cbf-632">taxnumber#</span></span>
  
<span data-ttu-id="52cbf-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="52cbf-633">taxnumber</span></span>
  
<span data-ttu-id="52cbf-634">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-634">tax id</span></span>
  
<span data-ttu-id="52cbf-635">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="52cbf-635">taxid#</span></span>
  
<span data-ttu-id="52cbf-636">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-636">tax identification number</span></span>
  
<span data-ttu-id="52cbf-637">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-637">tax identification no.</span></span>
  
<span data-ttu-id="52cbf-638">numru tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="52cbf-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="52cbf-639">ID tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="52cbf-639">id tat-taxxa</span></span>
  
<span data-ttu-id="52cbf-640">numru ta ' identifikazzjoni tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="52cbf-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="52cbf-641">Niederlande</span><span class="sxs-lookup"><span data-stu-id="52cbf-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-642">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-642">Format</span></span>

<span data-ttu-id="52cbf-643">Neun Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-644">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-644">Pattern</span></span>

<span data-ttu-id="52cbf-645">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="52cbf-646">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-646">Checksum</span></span>

<span data-ttu-id="52cbf-647">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-648">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-648">Definition</span></span>

<span data-ttu-id="52cbf-649">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-650">Die- `Func_netherlands_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-651">Ein Schlüsselwort `Keywords_netherlands_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-652">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-653">Die- `Func_netherlands_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-654">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="52cbf-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-656">niederländische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="52cbf-657">niederländische Steueridentifikation</span><span class="sxs-lookup"><span data-stu-id="52cbf-657">netherlands tax identification</span></span>
  
<span data-ttu-id="52cbf-658">niederländische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="52cbf-659">niederländische Steueridentifikation</span><span class="sxs-lookup"><span data-stu-id="52cbf-659">netherland's tax identification</span></span>
  
<span data-ttu-id="52cbf-660">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-660">tax identification number</span></span>
  
<span data-ttu-id="52cbf-661">niederländische Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-661">dutch tax id</span></span>
  
<span data-ttu-id="52cbf-662">niederländische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-662">dutch tax identification number</span></span>
  
<span data-ttu-id="52cbf-663">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-663">tax id</span></span>
  
<span data-ttu-id="52cbf-664">Steuer-ID #</span><span class="sxs-lookup"><span data-stu-id="52cbf-664">tax id#</span></span>
  
<span data-ttu-id="52cbf-665">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-665">tax number</span></span>
  
<span data-ttu-id="52cbf-666">Steuernummer #</span><span class="sxs-lookup"><span data-stu-id="52cbf-666">tax no#</span></span>
  
<span data-ttu-id="52cbf-667">Steuer #</span><span class="sxs-lookup"><span data-stu-id="52cbf-667">tax#</span></span>
  
<span data-ttu-id="52cbf-668">Zinn</span><span class="sxs-lookup"><span data-stu-id="52cbf-668">tin</span></span>
  
<span data-ttu-id="52cbf-669">Zinn #</span><span class="sxs-lookup"><span data-stu-id="52cbf-669">tin#</span></span>
  
<span data-ttu-id="52cbf-670">Niederlande Tin</span><span class="sxs-lookup"><span data-stu-id="52cbf-670">netherlands tin</span></span>
  
<span data-ttu-id="52cbf-671">niederländische Zinn</span><span class="sxs-lookup"><span data-stu-id="52cbf-671">netherland's tin</span></span>
  
<span data-ttu-id="52cbf-672">Nederlands belasten identificatienummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="52cbf-673">identificatienummer van belasten</span><span class="sxs-lookup"><span data-stu-id="52cbf-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="52cbf-674">identificatienummer-Belastungen</span><span class="sxs-lookup"><span data-stu-id="52cbf-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="52cbf-675">Nederlands belasten identificatie</span><span class="sxs-lookup"><span data-stu-id="52cbf-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="52cbf-676">Nederlands Belasting ID Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="52cbf-677">Nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="52cbf-678">BTW Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-678">btw nummer</span></span>
  
<span data-ttu-id="52cbf-679">Nederlandse belasten von identificatie</span><span class="sxs-lookup"><span data-stu-id="52cbf-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="52cbf-680">Polen</span><span class="sxs-lookup"><span data-stu-id="52cbf-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-681">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-681">Format</span></span>

<span data-ttu-id="52cbf-682">Elf Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-683">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-683">Pattern</span></span>

<span data-ttu-id="52cbf-684">Elf Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="52cbf-685">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-685">Checksum</span></span>

<span data-ttu-id="52cbf-686">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-687">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-687">Definition</span></span>

<span data-ttu-id="52cbf-688">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-689">Die- `Func_poland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-690">Ein Schlüsselwort `Keywords_poland_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-691">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-692">Die- `Func_poland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-693">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="52cbf-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-695">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-695">tax number</span></span>
  
<span data-ttu-id="52cbf-696">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-696">tax no.</span></span>
  
<span data-ttu-id="52cbf-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-697">taxno#</span></span>
  
<span data-ttu-id="52cbf-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="52cbf-698">taxnumber#</span></span>
  
<span data-ttu-id="52cbf-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="52cbf-699">taxnumber</span></span>
  
<span data-ttu-id="52cbf-700">NIP</span><span class="sxs-lookup"><span data-stu-id="52cbf-700">nip</span></span>
  
<span data-ttu-id="52cbf-701">NIP #</span><span class="sxs-lookup"><span data-stu-id="52cbf-701">nip#</span></span>
  
<span data-ttu-id="52cbf-702">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-702">tax id</span></span>
  
<span data-ttu-id="52cbf-703">Steuer-ID #</span><span class="sxs-lookup"><span data-stu-id="52cbf-703">tax id#</span></span>
  
<span data-ttu-id="52cbf-704">NIP-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-704">nip id</span></span>
  
<span data-ttu-id="52cbf-705">NIP-ID #</span><span class="sxs-lookup"><span data-stu-id="52cbf-705">nip id#</span></span>
  
<span data-ttu-id="52cbf-706">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-706">tax identification number</span></span>
  
<span data-ttu-id="52cbf-707">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-707">tax identification no.</span></span>
  
<span data-ttu-id="52cbf-708">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-708">vat number</span></span>
  
<span data-ttu-id="52cbf-709">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-709">vat no.</span></span>
  
<span data-ttu-id="52cbf-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-710">vatno#</span></span>
  
<span data-ttu-id="52cbf-711">USt-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-711">vat id</span></span>
  
<span data-ttu-id="52cbf-712">USt-ID #</span><span class="sxs-lookup"><span data-stu-id="52cbf-712">vat id#</span></span>
  
<span data-ttu-id="52cbf-713">Numer identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="52cbf-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="52cbf-714">Polski Numer identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="52cbf-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="52cbf-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="52cbf-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="52cbf-716">Portugal</span><span class="sxs-lookup"><span data-stu-id="52cbf-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-717">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-717">Format</span></span>

<span data-ttu-id="52cbf-718">Neun Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-719">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-719">Pattern</span></span>

<span data-ttu-id="52cbf-720">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="52cbf-721">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-721">Checksum</span></span>

<span data-ttu-id="52cbf-722">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-723">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-723">Definition</span></span>

<span data-ttu-id="52cbf-724">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-725">Die- `Func_portugal_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-726">Ein Schlüsselwort `Keywords_portugal_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-727">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-728">Die- `Func_portugal_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-729">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="52cbf-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-731">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-731">tax number</span></span>
  
<span data-ttu-id="52cbf-732">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-732">tax no.</span></span>
  
<span data-ttu-id="52cbf-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-733">taxno#</span></span>
  
<span data-ttu-id="52cbf-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="52cbf-734">taxnumber#</span></span>
  
<span data-ttu-id="52cbf-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="52cbf-735">taxnumber</span></span>
  
<span data-ttu-id="52cbf-736">NIF</span><span class="sxs-lookup"><span data-stu-id="52cbf-736">nif</span></span>
  
<span data-ttu-id="52cbf-737">NIF #</span><span class="sxs-lookup"><span data-stu-id="52cbf-737">nif#</span></span>
  
<span data-ttu-id="52cbf-738">numerisch-Geschäftsjahr</span><span class="sxs-lookup"><span data-stu-id="52cbf-738">numero fiscal</span></span>
  
<span data-ttu-id="52cbf-739">número de identificação Fiscal</span><span class="sxs-lookup"><span data-stu-id="52cbf-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="52cbf-740">Rumänien</span><span class="sxs-lookup"><span data-stu-id="52cbf-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-741">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-741">Format</span></span>

<span data-ttu-id="52cbf-742">13 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-743">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-743">Pattern</span></span>

<span data-ttu-id="52cbf-744">13 Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="52cbf-745">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-745">Checksum</span></span>

<span data-ttu-id="52cbf-746">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="52cbf-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-747">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-747">Definition</span></span>

<span data-ttu-id="52cbf-748">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-749">Der reguläre Ausdruck `Regex_romania_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-750">Ein Schlüsselwort `Keywords_romania_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-751">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="52cbf-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-753">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-753">tax id</span></span>
  
<span data-ttu-id="52cbf-754">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-754">tax id number</span></span>
  
<span data-ttu-id="52cbf-755">Steuerdatei Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-755">tax file no</span></span>
  
<span data-ttu-id="52cbf-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="52cbf-756">tax file number</span></span>
  
<span data-ttu-id="52cbf-757">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-757">tax no</span></span>
  
<span data-ttu-id="52cbf-758">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-758">tax number</span></span>
  
<span data-ttu-id="52cbf-759">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="52cbf-759">taxid#</span></span>
  
<span data-ttu-id="52cbf-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-760">taxno#</span></span>
  
<span data-ttu-id="52cbf-761">ID-UL taxei</span><span class="sxs-lookup"><span data-stu-id="52cbf-761">id-ul taxei</span></span>
  
<span data-ttu-id="52cbf-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="52cbf-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="52cbf-763">Slowakei</span><span class="sxs-lookup"><span data-stu-id="52cbf-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-764">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-764">Format</span></span>

<span data-ttu-id="52cbf-765">10 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-766">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-766">Pattern</span></span>

<span data-ttu-id="52cbf-767">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="52cbf-768">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-768">Checksum</span></span>

<span data-ttu-id="52cbf-769">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="52cbf-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-770">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-770">Definition</span></span>

<span data-ttu-id="52cbf-771">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-772">Der reguläre Ausdruck `Regex_slovakia_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-773">Ein Schlüsselwort `Keywords_slovakia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-774">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="52cbf-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-776">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-776">tax id</span></span>
  
<span data-ttu-id="52cbf-777">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-777">tax id number</span></span>
  
<span data-ttu-id="52cbf-778">Tin-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-778">tin id</span></span>
  
<span data-ttu-id="52cbf-779">Tin Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-779">tin no</span></span>
  
<span data-ttu-id="52cbf-780">Slowakische Tin-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-780">slovakian tin id</span></span>
  
<span data-ttu-id="52cbf-781">Zinn</span><span class="sxs-lookup"><span data-stu-id="52cbf-781">tin</span></span>
  
<span data-ttu-id="52cbf-782">Steuerdatei Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-782">tax file no</span></span>
  
<span data-ttu-id="52cbf-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="52cbf-783">tax file number</span></span>
  
<span data-ttu-id="52cbf-784">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-784">tax no</span></span>
  
<span data-ttu-id="52cbf-785">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-785">tax number</span></span>
  
<span data-ttu-id="52cbf-786">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="52cbf-786">taxid#</span></span>
  
<span data-ttu-id="52cbf-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-787">taxno#</span></span>
  
<span data-ttu-id="52cbf-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="52cbf-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="52cbf-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="52cbf-789">daňové číslo</span></span>
  
<span data-ttu-id="52cbf-790">Daňové číslo SÚBORU</span><span class="sxs-lookup"><span data-stu-id="52cbf-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="52cbf-791">Slowenien</span><span class="sxs-lookup"><span data-stu-id="52cbf-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-792">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-792">Format</span></span>

<span data-ttu-id="52cbf-793">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-794">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-794">Pattern</span></span>

<span data-ttu-id="52cbf-795">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="52cbf-796">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-796">Checksum</span></span>

<span data-ttu-id="52cbf-797">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-798">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-798">Definition</span></span>

<span data-ttu-id="52cbf-799">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-800">Die- `Func_slovenia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-801">Ein Schlüsselwort `Keywords_slovenia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-802">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-803">Die- `Func_slovenia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-804">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="52cbf-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-806">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-806">tax id</span></span>
  
<span data-ttu-id="52cbf-807">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-807">tax id number</span></span>
  
<span data-ttu-id="52cbf-808">Tin-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-808">tin id</span></span>
  
<span data-ttu-id="52cbf-809">Tin Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-809">tin no</span></span>
  
<span data-ttu-id="52cbf-810">slowenische Tin-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-810">slovenian tin id</span></span>
  
<span data-ttu-id="52cbf-811">Zinn</span><span class="sxs-lookup"><span data-stu-id="52cbf-811">tin</span></span>
  
<span data-ttu-id="52cbf-812">Steuerdatei Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-812">tax file no</span></span>
  
<span data-ttu-id="52cbf-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="52cbf-813">tax file number</span></span>
  
<span data-ttu-id="52cbf-814">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-814">tax no</span></span>
  
<span data-ttu-id="52cbf-815">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-815">tax number</span></span>
  
<span data-ttu-id="52cbf-816">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="52cbf-816">taxid#</span></span>
  
<span data-ttu-id="52cbf-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-817">taxno#</span></span>
  
<span data-ttu-id="52cbf-818">identifikacijska številka beim Davka</span><span class="sxs-lookup"><span data-stu-id="52cbf-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="52cbf-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="52cbf-819">davčna številka</span></span>
  
<span data-ttu-id="52cbf-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="52cbf-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="52cbf-821">Spanien</span><span class="sxs-lookup"><span data-stu-id="52cbf-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-822">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-822">Format</span></span>

<span data-ttu-id="52cbf-823">Sieben oder acht Ziffern und ein oder zwei Buchstaben im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-824">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-824">Pattern</span></span>

<span data-ttu-id="52cbf-825">Spanisch natürliche Personen mit einem nationalen spanischen Identitätsausweis:</span><span class="sxs-lookup"><span data-stu-id="52cbf-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="52cbf-826">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-826">Eight digits</span></span> 
    
- <span data-ttu-id="52cbf-827">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="52cbf-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="52cbf-828">Nicht-residente Spanier ohne einen nationalen Identitätsausweis in Spanien</span><span class="sxs-lookup"><span data-stu-id="52cbf-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="52cbf-829">Ein Großbuchstabe "L" (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="52cbf-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="52cbf-830">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="52cbf-830">Seven digits</span></span>
    
- <span data-ttu-id="52cbf-831">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="52cbf-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="52cbf-832">Ansässige Spanier unter 14 Jahren ohne einen nationalen spanischen Identitätsausweis:</span><span class="sxs-lookup"><span data-stu-id="52cbf-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="52cbf-833">Ein Großbuchstabe "K" (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="52cbf-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="52cbf-834">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="52cbf-834">Seven digits</span></span> 
    
- <span data-ttu-id="52cbf-835">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="52cbf-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="52cbf-836">Ausländer mit Identifikationsnummer eines Ausländers</span><span class="sxs-lookup"><span data-stu-id="52cbf-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="52cbf-837">Ein Großbuchstabe mit "X", "Y" oder "Z" (Groß-/Kleinschreibung wird beachtet)</span><span class="sxs-lookup"><span data-stu-id="52cbf-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="52cbf-838">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="52cbf-838">Seven digits</span></span>
    
- <span data-ttu-id="52cbf-839">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="52cbf-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="52cbf-840">Ausländer ohne Identifikationsnummer eines Ausländers</span><span class="sxs-lookup"><span data-stu-id="52cbf-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="52cbf-841">Ein Großbuchstabe, der "M" ist (Groß-/Kleinschreibung beachten)</span><span class="sxs-lookup"><span data-stu-id="52cbf-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="52cbf-842">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="52cbf-842">Seven digits</span></span>
    
- <span data-ttu-id="52cbf-843">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="52cbf-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="52cbf-844">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-844">Checksum</span></span>

<span data-ttu-id="52cbf-845">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-846">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-846">Definition</span></span>

<span data-ttu-id="52cbf-847">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-848">Die- `Func_spain_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-849">Ein Schlüsselwort `Keywords_spain_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-850">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-851">Die- `Func_spain_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-852">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="52cbf-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-854">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-854">tax id</span></span>
  
<span data-ttu-id="52cbf-855">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-855">tax id number</span></span>
  
<span data-ttu-id="52cbf-856">CIF-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-856">cif id</span></span>
  
<span data-ttu-id="52cbf-857">CIF Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-857">cif no</span></span>
  
<span data-ttu-id="52cbf-858">spanische CIF-ID</span><span class="sxs-lookup"><span data-stu-id="52cbf-858">spanish cif id</span></span>
  
<span data-ttu-id="52cbf-859">CIF</span><span class="sxs-lookup"><span data-stu-id="52cbf-859">cif</span></span>
  
<span data-ttu-id="52cbf-860">Steuerdatei Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-860">tax file no</span></span>
  
<span data-ttu-id="52cbf-861">spanische CIF-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-861">spanish cif number</span></span>
  
<span data-ttu-id="52cbf-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="52cbf-862">tax file number</span></span>
  
<span data-ttu-id="52cbf-863">Spanisch CIF Nein</span><span class="sxs-lookup"><span data-stu-id="52cbf-863">spanish cif no</span></span>
  
<span data-ttu-id="52cbf-864">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-864">tax no</span></span>
  
<span data-ttu-id="52cbf-865">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-865">tax number</span></span>
  
<span data-ttu-id="52cbf-866">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="52cbf-866">taxid#</span></span>
  
<span data-ttu-id="52cbf-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-867">taxno#</span></span>
  
<span data-ttu-id="52cbf-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="52cbf-868">cifid#</span></span>
  
<span data-ttu-id="52cbf-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="52cbf-869">spanishcifid#</span></span>
  
<span data-ttu-id="52cbf-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="52cbf-870">spanishcifno#</span></span>
  
<span data-ttu-id="52cbf-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="52cbf-871">número de contribuyente</span></span>
  
<span data-ttu-id="52cbf-872">número de Impuesto Corporativo</span><span class="sxs-lookup"><span data-stu-id="52cbf-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="52cbf-873">número de Identificación Fiscal</span><span class="sxs-lookup"><span data-stu-id="52cbf-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="52cbf-874">CIF-número</span><span class="sxs-lookup"><span data-stu-id="52cbf-874">cif número</span></span>
  
<span data-ttu-id="52cbf-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="52cbf-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="52cbf-876">Schweden</span><span class="sxs-lookup"><span data-stu-id="52cbf-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-877">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-877">Format</span></span>

<span data-ttu-id="52cbf-878">Zehn Ziffern und ein Symbol im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-879">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-879">Pattern</span></span>

<span data-ttu-id="52cbf-880">Zehn Ziffern und ein Symbol:</span><span class="sxs-lookup"><span data-stu-id="52cbf-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="52cbf-881">Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)</span><span class="sxs-lookup"><span data-stu-id="52cbf-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="52cbf-882">Pluszeichen, Minuszeichen oder Backslash</span><span class="sxs-lookup"><span data-stu-id="52cbf-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="52cbf-883">Drei Ziffern, die die Identifikationsnummer eindeutig machen:</span><span class="sxs-lookup"><span data-stu-id="52cbf-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="52cbf-884">Für Zahlen, die vor 1990 ausgegeben wurden, identifizieren die siebte und die achte Ziffer den Geburts Kreis oder den in der fremde geborenen Personen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="52cbf-885">Die Ziffer in der neunten Position gibt das Geschlecht entweder ungerade für männliche oder sogar für weiblich an.</span><span class="sxs-lookup"><span data-stu-id="52cbf-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="52cbf-886">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="52cbf-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="52cbf-887">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-887">Checksum</span></span>

<span data-ttu-id="52cbf-888">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-889">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-889">Definition</span></span>

<span data-ttu-id="52cbf-890">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-891">Die- `Func_sweden_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-892">Ein Schlüsselwort `Keywords_sweden_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="52cbf-893">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-894">Die- `Func_sweden_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-895">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="52cbf-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-897">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-897">tax id</span></span>
  
<span data-ttu-id="52cbf-898">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-898">tax id no.</span></span>
  
<span data-ttu-id="52cbf-899">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-899">tax id number</span></span>
  
<span data-ttu-id="52cbf-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="52cbf-900">tax identification</span></span>
  
<span data-ttu-id="52cbf-901">Steueridentifikation #</span><span class="sxs-lookup"><span data-stu-id="52cbf-901">tax identification#</span></span>
  
<span data-ttu-id="52cbf-902">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-902">tax no.</span></span>
  
<span data-ttu-id="52cbf-903">Steuer #</span><span class="sxs-lookup"><span data-stu-id="52cbf-903">tax#</span></span>
  
<span data-ttu-id="52cbf-904">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="52cbf-904">taxid#</span></span>
  
<span data-ttu-id="52cbf-905">Steuerdatei</span><span class="sxs-lookup"><span data-stu-id="52cbf-905">tax file</span></span>
  
<span data-ttu-id="52cbf-906">Steuerdatei-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-906">tax file no.</span></span>
  
<span data-ttu-id="52cbf-907">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-907">personal id number</span></span>
  
<span data-ttu-id="52cbf-908">Skate ID Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-908">skatt id nummer</span></span>
  
<span data-ttu-id="52cbf-909">skatt Identifikation</span><span class="sxs-lookup"><span data-stu-id="52cbf-909">skatt identifikation</span></span>
  
<span data-ttu-id="52cbf-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="52cbf-911">UK</span><span class="sxs-lookup"><span data-stu-id="52cbf-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="52cbf-912">Format</span><span class="sxs-lookup"><span data-stu-id="52cbf-912">Format</span></span>

<span data-ttu-id="52cbf-913">Unique Steuerzahler Referenz (UTR): 10 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="52cbf-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="52cbf-914">Nationale Versicherungsnummer (Nino): Weitere Informationen finden Sie im Abschnitt "U.K.</span><span class="sxs-lookup"><span data-stu-id="52cbf-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="52cbf-915">Nationale Versicherungsnummer (Nino) "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="52cbf-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="52cbf-916">Muster</span><span class="sxs-lookup"><span data-stu-id="52cbf-916">Pattern</span></span>

<span data-ttu-id="52cbf-917">Unique Steuerzahler Referenz (UTR): 10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="52cbf-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="52cbf-918">Nationale Versicherungsnummer (Nino): Weitere Informationen finden Sie im Abschnitt "U.K.</span><span class="sxs-lookup"><span data-stu-id="52cbf-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="52cbf-919">Nationale Versicherungsnummer (Nino) "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="52cbf-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="52cbf-920">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="52cbf-920">Checksum</span></span>

<span data-ttu-id="52cbf-921">Ja</span><span class="sxs-lookup"><span data-stu-id="52cbf-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="52cbf-922">Definition</span><span class="sxs-lookup"><span data-stu-id="52cbf-922">Definition</span></span>

<span data-ttu-id="52cbf-923">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52cbf-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="52cbf-924">Die- `Func_uk_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="52cbf-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="52cbf-925">Ein Schlüsselwort `Keywords_uk_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="52cbf-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="52cbf-926">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52cbf-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="52cbf-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="52cbf-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="52cbf-928">tax id</span><span class="sxs-lookup"><span data-stu-id="52cbf-928">tax id</span></span>
  
<span data-ttu-id="52cbf-929">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-929">tax id no.</span></span>
  
<span data-ttu-id="52cbf-930">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="52cbf-930">tax id number</span></span>
  
<span data-ttu-id="52cbf-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="52cbf-931">tax identification</span></span>
  
<span data-ttu-id="52cbf-932">Steueridentifikation #</span><span class="sxs-lookup"><span data-stu-id="52cbf-932">tax identification#</span></span>
  
<span data-ttu-id="52cbf-933">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-933">tax no.</span></span>
  
<span data-ttu-id="52cbf-934">Steuer #</span><span class="sxs-lookup"><span data-stu-id="52cbf-934">tax#</span></span>
  
<span data-ttu-id="52cbf-935">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="52cbf-935">taxid#</span></span>
  
<span data-ttu-id="52cbf-936">Steuerdatei</span><span class="sxs-lookup"><span data-stu-id="52cbf-936">tax file</span></span>
  
<span data-ttu-id="52cbf-937">Steuerdatei-Nr.</span><span class="sxs-lookup"><span data-stu-id="52cbf-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52cbf-938">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52cbf-938">See also</span></span>

[<span data-ttu-id="52cbf-939">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="52cbf-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

