---
title: EU-nationale Identifikationsnummer
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp "EU-nationale Identifikationsnummer" erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: f001d23ec3d6d8a2b3aa9575d4a9d602c4315e13
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592236"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="d6d36-104">EU-nationale Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-104">EU National Identification Number</span></span>

<span data-ttu-id="d6d36-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp "EU-nationale Identifikationsnummer" erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="d6d36-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="d6d36-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="d6d36-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="d6d36-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="d6d36-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-108">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-108">Format</span></span>

<span data-ttu-id="d6d36-109">Eine Kombination aus Buchstaben, Ziffern und Sonderzeichen mit einer 24 Zeichen Länge</span><span class="sxs-lookup"><span data-stu-id="d6d36-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-110">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-110">Pattern</span></span>

<span data-ttu-id="d6d36-111">24 Zeichen:</span><span class="sxs-lookup"><span data-stu-id="d6d36-111">24 characters:</span></span>
  
-  <span data-ttu-id="d6d36-112">22 Buchstaben (Unterscheidung nach Groß-/Kleinschreibung), Ziffern, umgekehrte Schrägstriche oder Pluszeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="d6d36-113">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet), Ziffern, Backslashes, Schrägstriche, Pluszeichen oder gleich Zeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d6d36-114">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-114">Checksum</span></span>

<span data-ttu-id="d6d36-115">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d6d36-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-116">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-116">Definition</span></span>

<span data-ttu-id="d6d36-117">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-118">Der reguläre Ausdruck `Regex_austria_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-119">Ein Schlüsselwort `Keywords_austria_eu_national_id_card` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-120">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-120">Keywords</span></span>

#### <a name="keywords_austria_eu_national_id_card"></a><span data-ttu-id="d6d36-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-122">Österreichische Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-122">austrian identity number</span></span>
  
<span data-ttu-id="d6d36-123">nationale Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-123">national identity number</span></span>
  
<span data-ttu-id="d6d36-124">Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-124">identity number</span></span>
  
<span data-ttu-id="d6d36-125">national id</span><span class="sxs-lookup"><span data-stu-id="d6d36-125">national id</span></span>
  
<span data-ttu-id="d6d36-126">Personalausweis Republik Österreich</span><span class="sxs-lookup"><span data-stu-id="d6d36-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="d6d36-127">Belgien</span><span class="sxs-lookup"><span data-stu-id="d6d36-127">Belgium</span></span>

<span data-ttu-id="d6d36-128">Ausführliche Informationen finden Sie im Abschnitt "belgische nationale Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d6d36-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="d6d36-129">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="d6d36-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-130">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-130">Format</span></span>

<span data-ttu-id="d6d36-131">Zehn Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-132">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-132">Pattern</span></span>

<span data-ttu-id="d6d36-133">Zehn Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="d6d36-134">Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)</span><span class="sxs-lookup"><span data-stu-id="d6d36-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="d6d36-135">Zwei Ziffern, die der Geburts Reihenfolge entsprechen</span><span class="sxs-lookup"><span data-stu-id="d6d36-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="d6d36-136">Eine Ziffer, die dem Geschlecht entspricht: eine gerade Ziffer für "männlich" und eine ungerade Ziffer für "weiblich".</span><span class="sxs-lookup"><span data-stu-id="d6d36-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="d6d36-137">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="d6d36-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d6d36-138">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-138">Checksum</span></span>

<span data-ttu-id="d6d36-139">Ja</span><span class="sxs-lookup"><span data-stu-id="d6d36-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-140">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-140">Definition</span></span>

<span data-ttu-id="d6d36-141">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-142">Die- `Func_bulgaria_national_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-143">Ein Schlüsselwort `Keywords_bulgaria_national_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="d6d36-144">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-145">Die- `Func_bulgaria_national_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-146">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-146">Keywords</span></span>

#### <a name="keywords_bulgaria_national_number"></a><span data-ttu-id="d6d36-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="d6d36-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="d6d36-148">EGN</span><span class="sxs-lookup"><span data-stu-id="d6d36-148">egn</span></span>
  
<span data-ttu-id="d6d36-149">EGN #</span><span class="sxs-lookup"><span data-stu-id="d6d36-149">egn#</span></span>
  
<span data-ttu-id="d6d36-150">Bulgarische Nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-150">bulgarian national number</span></span>
  
<span data-ttu-id="d6d36-151">nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-151">national number</span></span>
  
<span data-ttu-id="d6d36-152">social security number</span><span class="sxs-lookup"><span data-stu-id="d6d36-152">social security number</span></span>
  
<span data-ttu-id="d6d36-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="d6d36-153">nationalnumber#</span></span>
  
<span data-ttu-id="d6d36-154">SSN #</span><span class="sxs-lookup"><span data-stu-id="d6d36-154">ssn#</span></span>
  
<span data-ttu-id="d6d36-155">SSN</span><span class="sxs-lookup"><span data-stu-id="d6d36-155">ssn</span></span>
  
<span data-ttu-id="d6d36-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="d6d36-156">nationalnumber</span></span>
  
<span data-ttu-id="d6d36-157">BNN #</span><span class="sxs-lookup"><span data-stu-id="d6d36-157">bnn#</span></span>
  
<span data-ttu-id="d6d36-158">BNN</span><span class="sxs-lookup"><span data-stu-id="d6d36-158">bnn</span></span>
  
<span data-ttu-id="d6d36-159">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-159">personal id number</span></span>
  
<span data-ttu-id="d6d36-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d6d36-160">personalidnumber#</span></span>
  
<span data-ttu-id="d6d36-161">единен граждански номер</span><span class="sxs-lookup"><span data-stu-id="d6d36-161">единен граждански номер</span></span>
  
<span data-ttu-id="d6d36-162">edinen grazhdanski Nomen</span><span class="sxs-lookup"><span data-stu-id="d6d36-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="d6d36-163">егн</span><span class="sxs-lookup"><span data-stu-id="d6d36-163">егн</span></span>
  
<span data-ttu-id="d6d36-164">егн #</span><span class="sxs-lookup"><span data-stu-id="d6d36-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="d6d36-165">Kroatien</span><span class="sxs-lookup"><span data-stu-id="d6d36-165">Croatia</span></span>

<span data-ttu-id="d6d36-166">Ausführliche Informationen finden Sie im Abschnitt "kroatische Identitätsnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d6d36-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="d6d36-167">Zypern</span><span class="sxs-lookup"><span data-stu-id="d6d36-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-168">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-168">Format</span></span>

<span data-ttu-id="d6d36-169">Zehn Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-170">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-170">Pattern</span></span>

 <span data-ttu-id="d6d36-171">Zehn Ziffern</span><span class="sxs-lookup"><span data-stu-id="d6d36-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d6d36-172">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-172">Checksum</span></span>

<span data-ttu-id="d6d36-173">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d6d36-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-174">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-174">Definition</span></span>

<span data-ttu-id="d6d36-175">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-176">Der reguläre Ausdruck `Regex_cyprus_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-177">Ein Schlüsselwort `Keywords_cyprus_eu_national_id_card` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-178">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-178">Keywords</span></span>

#### <a name="keywords_cyprus_eu_national_id_card"></a><span data-ttu-id="d6d36-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-180">ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-180">id card number</span></span>
  
<span data-ttu-id="d6d36-181">national identification number</span><span class="sxs-lookup"><span data-stu-id="d6d36-181">national identification number</span></span>
  
<span data-ttu-id="d6d36-182">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-182">personal id number</span></span>
  
<span data-ttu-id="d6d36-183">Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-183">identity card number</span></span>
  
<span data-ttu-id="d6d36-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="d6d36-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="d6d36-185">Tschechien</span><span class="sxs-lookup"><span data-stu-id="d6d36-185">Czech Republic</span></span>

<span data-ttu-id="d6d36-186">Ausführliche Informationen finden Sie im Abschnitt "Tschechische Nationale Identitätsnummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d6d36-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="d6d36-187">Dänemark</span><span class="sxs-lookup"><span data-stu-id="d6d36-187">Denmark</span></span>

<span data-ttu-id="d6d36-188">Ausführliche Informationen finden Sie im Abschnitt "dänische persönliche Identifikationsnummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d6d36-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="d6d36-189">Estland</span><span class="sxs-lookup"><span data-stu-id="d6d36-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-190">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-190">Format</span></span>

<span data-ttu-id="d6d36-191">11 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-192">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-192">Pattern</span></span>

<span data-ttu-id="d6d36-193">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="d6d36-193">11 digits:</span></span>
  
- <span data-ttu-id="d6d36-194">Eine Ziffer, die Geschlecht und Jahrhundert der Geburt entspricht (ungerade Zahl männlich, gerade Zahl weiblich; 1-2:19. Jahrhundert; 3-4:20th Century; 5-6:21st Century)</span><span class="sxs-lookup"><span data-stu-id="d6d36-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="d6d36-195">Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)</span><span class="sxs-lookup"><span data-stu-id="d6d36-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="d6d36-196">Drei Ziffern, die einer Seriennummer entsprechen, die Personen trennt, die am gleichen Datum geboren wurden</span><span class="sxs-lookup"><span data-stu-id="d6d36-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="d6d36-197">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="d6d36-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d6d36-198">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-198">Checksum</span></span>

<span data-ttu-id="d6d36-199">Ja</span><span class="sxs-lookup"><span data-stu-id="d6d36-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-200">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-200">Definition</span></span>

<span data-ttu-id="d6d36-201">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-202">Die- `Func_estonia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-203">Ein Schlüsselwort `Keywords_estonia_eu_national_id_card` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d6d36-204">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-205">Die- `Func_estonia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-206">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-206">Keywords</span></span>

#### <a name="keywords_estonia_eu_national_id_card"></a><span data-ttu-id="d6d36-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-208">persönlicher Identifikationscode</span><span class="sxs-lookup"><span data-stu-id="d6d36-208">personal identification code</span></span>
  
<span data-ttu-id="d6d36-209">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-209">personal identification number</span></span>
  
<span data-ttu-id="d6d36-210">national identification number</span><span class="sxs-lookup"><span data-stu-id="d6d36-210">national identification number</span></span>
  
<span data-ttu-id="d6d36-211">nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-211">national number</span></span>
  
<span data-ttu-id="d6d36-212">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-212">personal id number</span></span>
  
<span data-ttu-id="d6d36-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d6d36-213">personalidnumber#</span></span>
  
<span data-ttu-id="d6d36-214">IK</span><span class="sxs-lookup"><span data-stu-id="d6d36-214">ik</span></span>
  
<span data-ttu-id="d6d36-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="d6d36-215">isikukood</span></span>
  
<span data-ttu-id="d6d36-216">ID-Kaart</span><span class="sxs-lookup"><span data-stu-id="d6d36-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="d6d36-217">Finnland</span><span class="sxs-lookup"><span data-stu-id="d6d36-217">Finland</span></span>

<span data-ttu-id="d6d36-218">Ausführliche Informationen finden Sie im Abschnitt "finnische nationale ID" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d6d36-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="d6d36-219">Frankreich</span><span class="sxs-lookup"><span data-stu-id="d6d36-219">France</span></span>

<span data-ttu-id="d6d36-220">Ausführliche Informationen finden Sie im Abschnitt "France National ID Card (CNI)" in [What the sensitive Information Types Look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d6d36-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="d6d36-221">Deutschland</span><span class="sxs-lookup"><span data-stu-id="d6d36-221">Germany</span></span>

<span data-ttu-id="d6d36-222">Ausführliche Informationen finden Sie im Abschnitt "Deutsche Identitätskartennummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d6d36-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="d6d36-223">Griechenland</span><span class="sxs-lookup"><span data-stu-id="d6d36-223">Greece</span></span>

<span data-ttu-id="d6d36-224">Ausführliche Informationen finden Sie im Abschnitt "Griechenland-National Ausweis" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d6d36-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="d6d36-225">Ungarn</span><span class="sxs-lookup"><span data-stu-id="d6d36-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-226">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-226">Format</span></span>

<span data-ttu-id="d6d36-227">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="d6d36-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-228">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-228">Pattern</span></span>

<span data-ttu-id="d6d36-229">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="d6d36-229">11 digits:</span></span>
  
-  <span data-ttu-id="d6d36-230">Eine Ziffer, die dem Geschlecht entspricht (1-männlich, 2-weiblich, andere Zahlen sind auch für Bürger möglich, die vor 1900 oder Bürgern mit doppelter Staatsbürgerschaft geboren wurden)</span><span class="sxs-lookup"><span data-stu-id="d6d36-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="d6d36-231">Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)</span><span class="sxs-lookup"><span data-stu-id="d6d36-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="d6d36-232">Drei Ziffern, die einer Seriennummer entsprechen</span><span class="sxs-lookup"><span data-stu-id="d6d36-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="d6d36-233">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="d6d36-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d6d36-234">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-234">Checksum</span></span>

<span data-ttu-id="d6d36-235">Ja</span><span class="sxs-lookup"><span data-stu-id="d6d36-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-236">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-236">Definition</span></span>

<span data-ttu-id="d6d36-237">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-238">Die- `Func_hungary_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-239">Ein Schlüsselwort `Keywords_hungary_eu_national_id_card` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d6d36-240">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-241">Die- `Func_hungary_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-242">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-242">Keywords</span></span>

#### <a name="keywords_hungary_eu_national_id_card"></a><span data-ttu-id="d6d36-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-244">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-244">personal identification number</span></span>
  
<span data-ttu-id="d6d36-245">identification number</span><span class="sxs-lookup"><span data-stu-id="d6d36-245">identification number</span></span>
  
<span data-ttu-id="d6d36-246">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-246">personal id number</span></span>
  
<span data-ttu-id="d6d36-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="d6d36-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="d6d36-248">Irland</span><span class="sxs-lookup"><span data-stu-id="d6d36-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-249">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-249">Format</span></span>

<span data-ttu-id="d6d36-250">Eine neunstellige Kombination aus Buchstaben, Ziffern und einem Leerzeichen im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-251">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-251">Pattern</span></span>

<span data-ttu-id="d6d36-252">Eine neunstellige Kombination aus Buchstaben, Ziffern und einem Leerzeichen im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="d6d36-253">Vom 01 Januar 2013 bis jetzt:</span><span class="sxs-lookup"><span data-stu-id="d6d36-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="d6d36-254">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="d6d36-254">Seven digits</span></span> 
    
- <span data-ttu-id="d6d36-255">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="d6d36-255">One check digit</span></span>
    
- <span data-ttu-id="d6d36-256">Ein Leerzeichen oder der Großbuchstabe "W" (Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="d6d36-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="d6d36-257">Vor dem 01. Januar 2013:</span><span class="sxs-lookup"><span data-stu-id="d6d36-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="d6d36-258">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="d6d36-258">Seven digits</span></span> 
    
- <span data-ttu-id="d6d36-259">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="d6d36-259">One check digit</span></span>
    
- <span data-ttu-id="d6d36-260">Ein Leerzeichen oder ein Großbuchstabe (Groß-/Kleinschreibung beachten)</span><span class="sxs-lookup"><span data-stu-id="d6d36-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d6d36-261">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-261">Checksum</span></span>

<span data-ttu-id="d6d36-262">Ja</span><span class="sxs-lookup"><span data-stu-id="d6d36-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-263">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-263">Definition</span></span>

<span data-ttu-id="d6d36-264">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-265">Die-Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="d6d36-266">Ein Schlüsselwort aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-266">A keyword from is found.</span></span>
    
<span data-ttu-id="d6d36-267">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-268">Die-Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-268">The function finds content that matches the pattern.</span></span>
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-269">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-269">Keywords</span></span>

#### <a name="keywords_ireland_eu_national_id_card"></a><span data-ttu-id="d6d36-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-271">persönliche öffentliche Dienstnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-271">personal public service number</span></span>
  
<span data-ttu-id="d6d36-272">PPS Nein</span><span class="sxs-lookup"><span data-stu-id="d6d36-272">pps no</span></span>
  
<span data-ttu-id="d6d36-273">Umsatz-und Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="d6d36-274">RSI-Nr.</span><span class="sxs-lookup"><span data-stu-id="d6d36-274">rsi no</span></span>
  
<span data-ttu-id="d6d36-275">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-275">personal identification number</span></span>
  
<span data-ttu-id="d6d36-276">identification number</span><span class="sxs-lookup"><span data-stu-id="d6d36-276">identification number</span></span>
  
<span data-ttu-id="d6d36-277">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-277">personal id number</span></span>
  
<span data-ttu-id="d6d36-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="d6d36-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="d6d36-279">uimh.</span><span class="sxs-lookup"><span data-stu-id="d6d36-279">uimh.</span></span> <span data-ttu-id="d6d36-280">PSP</span><span class="sxs-lookup"><span data-stu-id="d6d36-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="d6d36-281">Italien</span><span class="sxs-lookup"><span data-stu-id="d6d36-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-282">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-282">Format</span></span>

<span data-ttu-id="d6d36-283">Eine Kombination aus Buchstaben und Ziffern aus 16 Zeichen im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-284">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-284">Pattern</span></span>

<span data-ttu-id="d6d36-285">Eine Kombination aus Buchstaben und Ziffern aus 16 Zeichen:</span><span class="sxs-lookup"><span data-stu-id="d6d36-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="d6d36-286">Drei Buchstaben, die den ersten drei Konsonanten im Familiennamen entsprechen</span><span class="sxs-lookup"><span data-stu-id="d6d36-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="d6d36-287">Drei Buchstaben, die den ersten, dritten und vierten Konsonanten im Vornamen entsprechen</span><span class="sxs-lookup"><span data-stu-id="d6d36-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="d6d36-288">Zwei Ziffern, die den letzten Ziffern des Geburtsjahres entsprechen</span><span class="sxs-lookup"><span data-stu-id="d6d36-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="d6d36-289">Ein Buchstabe, der dem Brief für den Monat der Geburt entspricht – Buchstaben werden in alphabetischer Reihenfolge verwendet, aber nur die Buchstaben a bis E, H, L, M, P, R bis T werden verwendet (der Januar ist also a und Oktober ist r).</span><span class="sxs-lookup"><span data-stu-id="d6d36-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="d6d36-290">Zwei Ziffern, die dem Tag des Geburtsmonats entsprechen – um zwischen den Geschlechtern zu unterscheiden, wird 40 am Tag der Geburt für Frauen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d6d36-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="d6d36-291">Vier Ziffern, die der Ortskennzahl für die Gemeinde entsprechen, in der die Person geboren wurde (landesweite Codes werden für fremde Länder verwendet)</span><span class="sxs-lookup"><span data-stu-id="d6d36-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="d6d36-292">Eine Paritäts Ziffer</span><span class="sxs-lookup"><span data-stu-id="d6d36-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d6d36-293">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-293">Checksum</span></span>

<span data-ttu-id="d6d36-294">Ja</span><span class="sxs-lookup"><span data-stu-id="d6d36-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-295">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-295">Definition</span></span>

<span data-ttu-id="d6d36-296">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-297">Die- `Func_italy_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-298">Ein Schlüsselwort `Keywords_italy_eu_national_id_card` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d6d36-299">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-300">Die- `Func_italy_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-301">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-301">Keywords</span></span>

#### <a name="keywords_italy_eu_national_id_card"></a><span data-ttu-id="d6d36-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-303">persönlicher Code</span><span class="sxs-lookup"><span data-stu-id="d6d36-303">personal code</span></span>
  
<span data-ttu-id="d6d36-304">persönliche Codenummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-304">personal code number</span></span>
  
<span data-ttu-id="d6d36-305">persönliche Zertifikat Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-305">personal certificate number</span></span>
  
<span data-ttu-id="d6d36-306">Geschäftscode</span><span class="sxs-lookup"><span data-stu-id="d6d36-306">fiscal code</span></span>
  
<span data-ttu-id="d6d36-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="d6d36-307">personalcodeno#</span></span>
  
<span data-ttu-id="d6d36-308">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-308">personal id number</span></span>
  
<span data-ttu-id="d6d36-309">persönlicher ID-Code</span><span class="sxs-lookup"><span data-stu-id="d6d36-309">personal id code</span></span>
  
<span data-ttu-id="d6d36-310">Dice personale</span><span class="sxs-lookup"><span data-stu-id="d6d36-310">codice personale</span></span>
  
<span data-ttu-id="d6d36-311">Numero Bescheinigung personale</span><span class="sxs-lookup"><span data-stu-id="d6d36-311">numero certificato personale</span></span>
  
<span data-ttu-id="d6d36-312">Numero personale</span><span class="sxs-lookup"><span data-stu-id="d6d36-312">numero personale</span></span>
  
<span data-ttu-id="d6d36-313">Numero-ID personale</span><span class="sxs-lookup"><span data-stu-id="d6d36-313">numero id personale</span></span>
  
<span data-ttu-id="d6d36-314">Dice ID personale</span><span class="sxs-lookup"><span data-stu-id="d6d36-314">codice id personale</span></span>
  
<span data-ttu-id="d6d36-315">Geschäftsjahr</span><span class="sxs-lookup"><span data-stu-id="d6d36-315">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="d6d36-316">Lettland</span><span class="sxs-lookup"><span data-stu-id="d6d36-316">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-317">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-317">Format</span></span>

<span data-ttu-id="d6d36-318">11 Ziffern und ein Bindestrich im angegebenen Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-319">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-319">Pattern</span></span>

<span data-ttu-id="d6d36-320">11 Ziffern und Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="d6d36-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="d6d36-321">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="d6d36-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="d6d36-322">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="d6d36-322">A hyphen</span></span>
    
- <span data-ttu-id="d6d36-323">Eine Ziffer, die dem Jahrhundert der Geburt entspricht ("0" für das 19. Jahrhundert, "1" für das 20. Jahrhundert und "2" für das 21. Jahrhundert)</span><span class="sxs-lookup"><span data-stu-id="d6d36-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="d6d36-324">Vier Ziffern, nach dem Zufallsprinzip generiert</span><span class="sxs-lookup"><span data-stu-id="d6d36-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d6d36-325">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-325">Checksum</span></span>

<span data-ttu-id="d6d36-326">Ja</span><span class="sxs-lookup"><span data-stu-id="d6d36-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-327">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-327">Definition</span></span>

<span data-ttu-id="d6d36-328">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-329">Die- `Func_latvia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-330">Ein Schlüsselwort `Keywords_latvia_eu_national_id_card` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d6d36-331">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-332">Die- `Func_latvia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-333">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-333">Keywords</span></span>

#### <a name="keywords_latvia_eu_national_id_card"></a><span data-ttu-id="d6d36-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-335">persönlicher Code</span><span class="sxs-lookup"><span data-stu-id="d6d36-335">personal code</span></span>
  
<span data-ttu-id="d6d36-336">persönliche Codenummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-336">personal code number</span></span>
  
<span data-ttu-id="d6d36-337">persönliche Zertifikat Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-337">personal certificate number</span></span>
  
<span data-ttu-id="d6d36-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="d6d36-338">personalcodeno#</span></span>
  
<span data-ttu-id="d6d36-339">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-339">personal id number</span></span>
  
<span data-ttu-id="d6d36-340">persönlicher ID-Code</span><span class="sxs-lookup"><span data-stu-id="d6d36-340">personal id code</span></span>
  
<span data-ttu-id="d6d36-341">Personas KODS</span><span class="sxs-lookup"><span data-stu-id="d6d36-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="d6d36-342">Litauen</span><span class="sxs-lookup"><span data-stu-id="d6d36-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-343">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-343">Format</span></span>

<span data-ttu-id="d6d36-344">11 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-345">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-345">Pattern</span></span>

<span data-ttu-id="d6d36-346">11 Ziffern ohne Leerzeichen und Trennzeichen:</span><span class="sxs-lookup"><span data-stu-id="d6d36-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="d6d36-347">Eine Ziffer, die dem Geschlecht der Person und dem Jahrhundert der Geburt entspricht</span><span class="sxs-lookup"><span data-stu-id="d6d36-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="d6d36-348">Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)</span><span class="sxs-lookup"><span data-stu-id="d6d36-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="d6d36-349">Drei Ziffern, die der Seriennummer des Geburtsdatums entsprechen</span><span class="sxs-lookup"><span data-stu-id="d6d36-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="d6d36-350">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="d6d36-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d6d36-351">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-351">Checksum</span></span>

<span data-ttu-id="d6d36-352">Ja</span><span class="sxs-lookup"><span data-stu-id="d6d36-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-353">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-353">Definition</span></span>

<span data-ttu-id="d6d36-354">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-355">Die- `Func_lithuania_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-356">Ein Schlüsselwort `Keywords_lithuania_eu_national_id_card` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d6d36-357">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-358">Die- `Func_lithuania_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-359">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-359">Keywords</span></span>

#### <a name="keywords_lithuania_eu_national_id_card"></a><span data-ttu-id="d6d36-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-361">persönlicher numerischer Code</span><span class="sxs-lookup"><span data-stu-id="d6d36-361">personal numeric code</span></span>
  
<span data-ttu-id="d6d36-362">eindeutige Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-362">unique identification number</span></span>
  
<span data-ttu-id="d6d36-363">Bürgerdienst Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-363">citizen service number</span></span>
  
<span data-ttu-id="d6d36-364">eindeutige Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-364">unique identity number</span></span>
  
<span data-ttu-id="d6d36-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="d6d36-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="d6d36-366">persönlicher Code.</span><span class="sxs-lookup"><span data-stu-id="d6d36-366">personal code.</span></span>
  
<span data-ttu-id="d6d36-367">asmeninis skaitmeninis KODAS</span><span class="sxs-lookup"><span data-stu-id="d6d36-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="d6d36-368">unikalus identifikavimo Numeris</span><span class="sxs-lookup"><span data-stu-id="d6d36-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="d6d36-369">piliečio paslaugos Numeris</span><span class="sxs-lookup"><span data-stu-id="d6d36-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="d6d36-370">unikalus identifikavimo KODAS</span><span class="sxs-lookup"><span data-stu-id="d6d36-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="d6d36-371">Mens KODAS.</span><span class="sxs-lookup"><span data-stu-id="d6d36-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="d6d36-372">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="d6d36-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-373">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-373">Format</span></span>

<span data-ttu-id="d6d36-374">11 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-375">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-375">Pattern</span></span>

<span data-ttu-id="d6d36-376">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="d6d36-376">11 digits</span></span>
  
- <span data-ttu-id="d6d36-377">Eine Ziffer, die dem Geschlecht der Person und dem Jahrhundert der Geburt entspricht</span><span class="sxs-lookup"><span data-stu-id="d6d36-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="d6d36-378">Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)</span><span class="sxs-lookup"><span data-stu-id="d6d36-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="d6d36-379">Drei Ziffern, die der Seriennummer des Geburtsdatums entsprechen</span><span class="sxs-lookup"><span data-stu-id="d6d36-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="d6d36-380">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="d6d36-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d6d36-381">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-381">Checksum</span></span>

<span data-ttu-id="d6d36-382">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d6d36-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-383">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-383">Definition</span></span>

<span data-ttu-id="d6d36-384">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-385">Der reguläre Ausdruck `Regex_luxemburg_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-386">Ein Schlüsselwort `Keywords_luxemburg_eu_national_id_card` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-387">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-387">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_national_id_card"></a><span data-ttu-id="d6d36-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-389">persönliche ID</span><span class="sxs-lookup"><span data-stu-id="d6d36-389">personal id</span></span>
  
<span data-ttu-id="d6d36-390">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-390">personal id number</span></span>
  
<span data-ttu-id="d6d36-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="d6d36-391">personalidno#</span></span>
  
<span data-ttu-id="d6d36-392">eindeutige ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-392">unique id number</span></span>
  
<span data-ttu-id="d6d36-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d6d36-393">personalidnumber#</span></span>
  
<span data-ttu-id="d6d36-394">eindeutiger ID-Schlüssel</span><span class="sxs-lookup"><span data-stu-id="d6d36-394">unique id key</span></span>
  
<span data-ttu-id="d6d36-395">persönlicher ID-Code</span><span class="sxs-lookup"><span data-stu-id="d6d36-395">personal id code</span></span>
  
<span data-ttu-id="d6d36-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="d6d36-396">uniqueidkey#</span></span>
  
<span data-ttu-id="d6d36-397">einzelner Code</span><span class="sxs-lookup"><span data-stu-id="d6d36-397">individual code</span></span>
  
<span data-ttu-id="d6d36-398">individuelle ID</span><span class="sxs-lookup"><span data-stu-id="d6d36-398">individual id</span></span>
  
<span data-ttu-id="d6d36-399">eindeutige-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="d6d36-400">eindeutige-ID</span><span class="sxs-lookup"><span data-stu-id="d6d36-400">eindeutige id</span></span>
  
<span data-ttu-id="d6d36-401">ID personnelle</span><span class="sxs-lookup"><span data-stu-id="d6d36-401">id personnelle</span></span>
  
<span data-ttu-id="d6d36-402">Numéro-d'identification-Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="d6d36-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="d6d36-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="d6d36-403">idpersonnelle#</span></span>
  
<span data-ttu-id="d6d36-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="d6d36-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="d6d36-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="d6d36-406">Malta</span><span class="sxs-lookup"><span data-stu-id="d6d36-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-407">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-407">Format</span></span>

<span data-ttu-id="d6d36-408">Sieben Ziffern, gefolgt von einem Buchstaben</span><span class="sxs-lookup"><span data-stu-id="d6d36-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-409">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-409">Pattern</span></span>

<span data-ttu-id="d6d36-410">Sieben Ziffern, gefolgt von einem Buchstaben:</span><span class="sxs-lookup"><span data-stu-id="d6d36-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="d6d36-411">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="d6d36-411">Seven digits</span></span> 
    
- <span data-ttu-id="d6d36-412">Ein Großbuchstabe (Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="d6d36-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d6d36-413">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-413">Checksum</span></span>

<span data-ttu-id="d6d36-414">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d6d36-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-415">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-415">Definition</span></span>

<span data-ttu-id="d6d36-416">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-417">Der reguläre Ausdruck `Regex_malta_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-418">Ein Schlüsselwort `Keywords_malta_eu_national_id_card` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d6d36-419">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-420">Der reguläre Ausdruck `Regex_malta_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-421">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-421">Keywords</span></span>

#### <a name="keywords_malta_eu_national_id_card"></a><span data-ttu-id="d6d36-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-423">persönlicher numerischer Code</span><span class="sxs-lookup"><span data-stu-id="d6d36-423">personal numeric code</span></span>
  
<span data-ttu-id="d6d36-424">eindeutige Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-424">unique identification number</span></span>
  
<span data-ttu-id="d6d36-425">Bürgerdienst Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-425">citizen service number</span></span>
  
<span data-ttu-id="d6d36-426">eindeutige Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-426">unique identity number</span></span>
  
<span data-ttu-id="d6d36-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="d6d36-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="d6d36-428">Kodiċi Numeri personali</span><span class="sxs-lookup"><span data-stu-id="d6d36-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="d6d36-429">numru ta ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="d6d36-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="d6d36-430">numru TAS-servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="d6d36-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="d6d36-431">numru ta ' identità uniku</span><span class="sxs-lookup"><span data-stu-id="d6d36-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="d6d36-432">Niederlande</span><span class="sxs-lookup"><span data-stu-id="d6d36-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-433">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-433">Format</span></span>

<span data-ttu-id="d6d36-434">Neun Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-435">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-435">Pattern</span></span>

<span data-ttu-id="d6d36-436">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="d6d36-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d6d36-437">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-437">Checksum</span></span>

<span data-ttu-id="d6d36-438">Ja</span><span class="sxs-lookup"><span data-stu-id="d6d36-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-439">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-439">Definition</span></span>

<span data-ttu-id="d6d36-440">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-441">Die- `Func_netherlands_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-442">Ein Schlüsselwort aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-442">A keyword from is found.</span></span>
    
<span data-ttu-id="d6d36-443">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-444">Die- `Func_netherlands_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-445">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-445">Keywords</span></span>

#### <a name="keywords_netherlands_eu_national_id_card"></a><span data-ttu-id="d6d36-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-447">persönlicher numerischer Code</span><span class="sxs-lookup"><span data-stu-id="d6d36-447">personal numeric code</span></span>
  
<span data-ttu-id="d6d36-448">eindeutige Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-448">unique identification number</span></span>
  
<span data-ttu-id="d6d36-449">Bürgerdienst Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-449">citizen service number</span></span>
  
<span data-ttu-id="d6d36-450">eindeutige Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-450">unique identity number</span></span>
  
<span data-ttu-id="d6d36-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="d6d36-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="d6d36-452">BSN</span><span class="sxs-lookup"><span data-stu-id="d6d36-452">bsn</span></span>
  
<span data-ttu-id="d6d36-453">BSN #</span><span class="sxs-lookup"><span data-stu-id="d6d36-453">bsn#</span></span>
  
<span data-ttu-id="d6d36-454">Persoonlijke-numerieke-Code</span><span class="sxs-lookup"><span data-stu-id="d6d36-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="d6d36-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="d6d36-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-456">burgerservicenummer</span></span>
  
<span data-ttu-id="d6d36-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="d6d36-458">Polen</span><span class="sxs-lookup"><span data-stu-id="d6d36-458">Poland</span></span>

<span data-ttu-id="d6d36-459">Ausführliche Informationen finden Sie im Abschnitt "Poland National ID (PESEL)" in [What the sensitive Information Types Look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d6d36-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="d6d36-460">Portugal</span><span class="sxs-lookup"><span data-stu-id="d6d36-460">Portugal</span></span>

<span data-ttu-id="d6d36-461">Ausführliche Informationen finden Sie im Abschnitt "Portugal-Bürgerkarten Nummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d6d36-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="d6d36-462">Rumänien</span><span class="sxs-lookup"><span data-stu-id="d6d36-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-463">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-463">Format</span></span>

<span data-ttu-id="d6d36-464">13 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-465">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-465">Pattern</span></span>

<span data-ttu-id="d6d36-466">13 Ziffern</span><span class="sxs-lookup"><span data-stu-id="d6d36-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d6d36-467">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-467">Checksum</span></span>

<span data-ttu-id="d6d36-468">Ja</span><span class="sxs-lookup"><span data-stu-id="d6d36-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-469">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-469">Definition</span></span>

<span data-ttu-id="d6d36-470">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-471">Die- `Func_romania_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-472">Ein Schlüsselwort `Keywords_romania_eu_national_id_card` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d6d36-473">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-474">Die- `Func_romania_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-475">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-475">Keywords</span></span>

#### <a name="keywords_romania_eu_national_id_card"></a><span data-ttu-id="d6d36-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-477">persönlicher numerischer Code</span><span class="sxs-lookup"><span data-stu-id="d6d36-477">personal numeric code</span></span>
  
<span data-ttu-id="d6d36-478">eindeutige Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-478">unique identification number</span></span>
  
<span data-ttu-id="d6d36-479">CNP</span><span class="sxs-lookup"><span data-stu-id="d6d36-479">cnp</span></span>
  
<span data-ttu-id="d6d36-480">CNP #</span><span class="sxs-lookup"><span data-stu-id="d6d36-480">cnp#</span></span>
  
<span data-ttu-id="d6d36-481">PIN</span><span class="sxs-lookup"><span data-stu-id="d6d36-481">pin</span></span>
  
<span data-ttu-id="d6d36-482">PIN #</span><span class="sxs-lookup"><span data-stu-id="d6d36-482">pin#</span></span>
  
<span data-ttu-id="d6d36-483">Versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-483">insurance number</span></span>
  
<span data-ttu-id="d6d36-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="d6d36-484">insurancenumber#</span></span>
  
<span data-ttu-id="d6d36-485">eindeutige Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-485">unique identity number</span></span>
  
<span data-ttu-id="d6d36-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="d6d36-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="d6d36-487">COD numerisch persönlich</span><span class="sxs-lookup"><span data-stu-id="d6d36-487">cod numeric personal</span></span>
  
<span data-ttu-id="d6d36-488">COD identificare Personal</span><span class="sxs-lookup"><span data-stu-id="d6d36-488">cod identificare personal</span></span>
  
<span data-ttu-id="d6d36-489">COD Unic identificare</span><span class="sxs-lookup"><span data-stu-id="d6d36-489">cod unic identificare</span></span>
  
<span data-ttu-id="d6d36-490">număr Personal Unic</span><span class="sxs-lookup"><span data-stu-id="d6d36-490">număr personal unic</span></span>
  
<span data-ttu-id="d6d36-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="d6d36-491">număr identitate</span></span>
  
<span data-ttu-id="d6d36-492">număr identificare Personal</span><span class="sxs-lookup"><span data-stu-id="d6d36-492">număr identificare personal</span></span>
  
<span data-ttu-id="d6d36-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="d6d36-493">număridentitate#</span></span>
  
<span data-ttu-id="d6d36-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="d6d36-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="d6d36-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="d6d36-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="d6d36-496">Slowakei</span><span class="sxs-lookup"><span data-stu-id="d6d36-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-497">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-497">Format</span></span>

<span data-ttu-id="d6d36-498">Zehn Ziffern mit einem Backslash</span><span class="sxs-lookup"><span data-stu-id="d6d36-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-499">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-499">Pattern</span></span>

<span data-ttu-id="d6d36-500">Zehn Ziffern mit einem Backslash:</span><span class="sxs-lookup"><span data-stu-id="d6d36-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d6d36-501">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-501">Checksum</span></span>

<span data-ttu-id="d6d36-502">Ja</span><span class="sxs-lookup"><span data-stu-id="d6d36-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-503">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-503">Definition</span></span>

<span data-ttu-id="d6d36-504">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-505">Die- `Func_slovakia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-506">Ein Schlüsselwort `Keywords_slovakia_eu_national_id_card` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d6d36-507">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-508">Die- `Func_slovakia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-509">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-509">Keywords</span></span>

#### <a name="keywords_slovakia_eu_national_id_card"></a><span data-ttu-id="d6d36-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-511">Geburtsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-511">birth number</span></span>
  
<span data-ttu-id="d6d36-512">national identification number</span><span class="sxs-lookup"><span data-stu-id="d6d36-512">national identification number</span></span>
  
<span data-ttu-id="d6d36-513">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-513">personal identification number</span></span>
  
<span data-ttu-id="d6d36-514">social security number</span><span class="sxs-lookup"><span data-stu-id="d6d36-514">social security number</span></span>
  
<span data-ttu-id="d6d36-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="d6d36-515">nationalnumber#</span></span>
  
<span data-ttu-id="d6d36-516">SSN #</span><span class="sxs-lookup"><span data-stu-id="d6d36-516">ssn#</span></span>
  
<span data-ttu-id="d6d36-517">SSN</span><span class="sxs-lookup"><span data-stu-id="d6d36-517">ssn</span></span>
  
<span data-ttu-id="d6d36-518">nationale Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-518">national number</span></span>
  
<span data-ttu-id="d6d36-519">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-519">personal id number</span></span>
  
<span data-ttu-id="d6d36-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d6d36-520">personalidnumber#</span></span>
  
<span data-ttu-id="d6d36-521">rč</span><span class="sxs-lookup"><span data-stu-id="d6d36-521">rč</span></span>
  
<span data-ttu-id="d6d36-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="d6d36-522">rodné číslo</span></span>
  
<span data-ttu-id="d6d36-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="d6d36-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="d6d36-524">Slowenien</span><span class="sxs-lookup"><span data-stu-id="d6d36-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-525">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-525">Format</span></span>

<span data-ttu-id="d6d36-526">13 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-527">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-527">Pattern</span></span>

<span data-ttu-id="d6d36-528">13 Ziffern im angegebenen Muster:</span><span class="sxs-lookup"><span data-stu-id="d6d36-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="d6d36-529">Sieben Ziffern, die dem Geburtsdatum (DDMMLLL) entsprechen, wobei "LLL" den letzten drei Ziffern des Geburtsjahres entspricht.</span><span class="sxs-lookup"><span data-stu-id="d6d36-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="d6d36-530">Zwei Ziffern, die dem Geburts Bereich entsprechen</span><span class="sxs-lookup"><span data-stu-id="d6d36-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="d6d36-531">Drei Ziffern, die einer Kombination aus Geschlecht und Seriennummer für Personen entsprechen, die am selben Tag geboren wurden (000-499 für männliche und 500-999 für weiblich)</span><span class="sxs-lookup"><span data-stu-id="d6d36-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="d6d36-532">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="d6d36-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d6d36-533">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-533">Checksum</span></span>

<span data-ttu-id="d6d36-534">Ja</span><span class="sxs-lookup"><span data-stu-id="d6d36-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-535">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-535">Definition</span></span>

<span data-ttu-id="d6d36-536">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-537">Die- `Func_slovenia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-538">Ein Schlüsselwort `Keywords_slovenia_eu_national_id_card` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d6d36-539">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-540">Die- `Func_slovenia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-541">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-541">Keywords</span></span>

#### <a name="keywords_slovenia_eu_national_id_card"></a><span data-ttu-id="d6d36-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-543">persönlicher numerischer Code</span><span class="sxs-lookup"><span data-stu-id="d6d36-543">personal numeric code</span></span>
  
<span data-ttu-id="d6d36-544">eindeutige Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-544">unique identification number</span></span>
  
<span data-ttu-id="d6d36-545">eindeutige Registrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-545">unique registration number</span></span>
  
<span data-ttu-id="d6d36-546">eindeutige Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-546">unique identity number</span></span>
  
<span data-ttu-id="d6d36-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="d6d36-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="d6d36-548">eindeutige Master Bürgerzahl</span><span class="sxs-lookup"><span data-stu-id="d6d36-548">unique master citizen number</span></span>
  
<span data-ttu-id="d6d36-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="d6d36-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="d6d36-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="d6d36-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="d6d36-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="d6d36-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="d6d36-552">EMŠO</span><span class="sxs-lookup"><span data-stu-id="d6d36-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="d6d36-553">Spanien</span><span class="sxs-lookup"><span data-stu-id="d6d36-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="d6d36-554">Format</span><span class="sxs-lookup"><span data-stu-id="d6d36-554">Format</span></span>

<span data-ttu-id="d6d36-555">Sieben Ziffern, gefolgt von einem Zeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d6d36-556">Muster</span><span class="sxs-lookup"><span data-stu-id="d6d36-556">Pattern</span></span>

<span data-ttu-id="d6d36-557">Sieben Ziffern, gefolgt von einem Zeichen</span><span class="sxs-lookup"><span data-stu-id="d6d36-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="d6d36-558">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="d6d36-558">Seven digits</span></span>
    
- <span data-ttu-id="d6d36-559">Eine Ziffer oder ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="d6d36-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d6d36-560">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="d6d36-560">Checksum</span></span>

<span data-ttu-id="d6d36-561">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d6d36-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d6d36-562">Definition</span><span class="sxs-lookup"><span data-stu-id="d6d36-562">Definition</span></span>

<span data-ttu-id="d6d36-563">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6d36-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d6d36-564">Der reguläre Ausdruck `Regex_spain_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d6d36-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d6d36-565">Ein Schlüsselwort `Keywords_spain_eu_national_id_card"` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="d6d36-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d6d36-566">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d36-566">Keywords</span></span>

#### <a name="keywords_spain_eu_national_id_card"></a><span data-ttu-id="d6d36-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d6d36-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="d6d36-568">DNI</span><span class="sxs-lookup"><span data-stu-id="d6d36-568">dni</span></span>
  
<span data-ttu-id="d6d36-569">national identification number</span><span class="sxs-lookup"><span data-stu-id="d6d36-569">national identification number</span></span>
  
<span data-ttu-id="d6d36-570">nationale Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-570">national identity number</span></span>
  
<span data-ttu-id="d6d36-571">Versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-571">insurance number</span></span>
  
<span data-ttu-id="d6d36-572">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-572">personal identification number</span></span>
  
<span data-ttu-id="d6d36-573">nationale Identität</span><span class="sxs-lookup"><span data-stu-id="d6d36-573">national identity</span></span>
  
<span data-ttu-id="d6d36-574">persönliche Identität Nein</span><span class="sxs-lookup"><span data-stu-id="d6d36-574">personal identity no</span></span>
  
<span data-ttu-id="d6d36-575">eindeutige Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="d6d36-575">unique identity number</span></span>
  
<span data-ttu-id="d6d36-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="d6d36-576">nationalidno#</span></span>
  
<span data-ttu-id="d6d36-577">UniqueId #</span><span class="sxs-lookup"><span data-stu-id="d6d36-577">uniqueid#</span></span>
  
<span data-ttu-id="d6d36-578">DNI #</span><span class="sxs-lookup"><span data-stu-id="d6d36-578">dni#</span></span>
  
<span data-ttu-id="d6d36-579">National-Nr. #</span><span class="sxs-lookup"><span data-stu-id="d6d36-579">nationalid#</span></span>
  
<span data-ttu-id="d6d36-580">nie #</span><span class="sxs-lookup"><span data-stu-id="d6d36-580">nie#</span></span>
  
<span data-ttu-id="d6d36-581">nie</span><span class="sxs-lookup"><span data-stu-id="d6d36-581">nie</span></span>
  
<span data-ttu-id="d6d36-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="d6d36-582">nienúmero#</span></span>
  
<span data-ttu-id="d6d36-583">nie número</span><span class="sxs-lookup"><span data-stu-id="d6d36-583">nie número</span></span>
  
<span data-ttu-id="d6d36-584">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="d6d36-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="d6d36-585">Identidad Único</span><span class="sxs-lookup"><span data-stu-id="d6d36-585">identidad único</span></span>
  
<span data-ttu-id="d6d36-586">número Nacional Identidad</span><span class="sxs-lookup"><span data-stu-id="d6d36-586">número nacional identidad</span></span>
  
<span data-ttu-id="d6d36-587">DNI número</span><span class="sxs-lookup"><span data-stu-id="d6d36-587">dni número</span></span>
  
<span data-ttu-id="d6d36-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="d6d36-588">dninúmero#</span></span>
  
<span data-ttu-id="d6d36-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="d6d36-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="d6d36-590">Schweden</span><span class="sxs-lookup"><span data-stu-id="d6d36-590">Sweden</span></span>

<span data-ttu-id="d6d36-591">Ausführliche Informationen finden Sie im Abschnitt "Sweden National ID" unter [What the sensitive Information Types Look](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d6d36-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d6d36-592">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6d36-592">See also</span></span>

[<span data-ttu-id="d6d36-593">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="d6d36-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

