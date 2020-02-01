---
title: Wonach die DLP-Funktionen suchen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Die Typen vertraulicher Informationen suchen nach einem bestimmten Muster und bestätigen es, indem Sie eine ordnungsgemäße Formatierung sicherstellen, Prüfsummen erzwingen und nach relevanten Schlüsselwörtern oder anderen Informationen suchen. Einige dieser Funktionen werden von internen Funktionen ausgeführt. In diesem Thema wird erläutert, wonach diese Funktionen suchen, damit Sie besser verstehen, wie die vordefinierten Typen vertraulicher Informationen funktionieren.
ms.openlocfilehash: 86ce1c9d546f776e239fdaca76219129c24a73e8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601202"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="8633b-105">Wonach die DLP-Funktionen suchen</span><span class="sxs-lookup"><span data-stu-id="8633b-105">What the DLP functions look for</span></span>

<span data-ttu-id="8633b-106">Die Verhinderung von Datenverlust (DLP) umfasst vertrauliche Informationstypen wie Kreditkartennummer und EU-Debitkarten-Nummer, die Sie in ihren DLP-Richtlinien verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8633b-106">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="8633b-107">Diese Typen vertraulicher Informationen suchen nach einem bestimmten Muster und bestätigen es, indem Sie eine ordnungsgemäße Formatierung sicherstellen, Prüfsummen erzwingen und nach relevanten Schlüsselwörtern oder anderen Informationen suchen.</span><span class="sxs-lookup"><span data-stu-id="8633b-107">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="8633b-108">Einige dieser Funktionen werden von internen Funktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8633b-108">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="8633b-109">Der vertrauliche Informationstyp Kreditkartennummer verwendet beispielsweise eine Funktion, um nach Datumsangaben zu suchen, die wie ein Ablaufdatum formatiert sind, um zu bestätigen, dass eine Zahl eine Kreditkartennummer ist.</span><span class="sxs-lookup"><span data-stu-id="8633b-109">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="8633b-110">In diesem Thema wird erläutert, wonach diese Funktionen suchen, damit Sie besser verstehen, wie die vordefinierten Typen vertraulicher Informationen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="8633b-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="8633b-111">Weitere Informationen finden Sie unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8633b-111">For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="8633b-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="8633b-112">Func_us_date</span></span>

<span data-ttu-id="8633b-113">Diese Funktion sucht nach einem Datum in dem Format, das in den USA häufig verwendet wird. Dies umfasst die Formate "Monat/Tag/Jahr", "Monat-Tag-Jahr" und "Monat Tag Jahr".</span><span class="sxs-lookup"><span data-stu-id="8633b-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="8633b-114">Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="8633b-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="8633b-115">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="8633b-115">Examples:</span></span>
  
- <span data-ttu-id="8633b-116">2. Dezember 2016</span><span class="sxs-lookup"><span data-stu-id="8633b-116">December 2, 2016</span></span>
    
- <span data-ttu-id="8633b-117">2. Dezember 2016</span><span class="sxs-lookup"><span data-stu-id="8633b-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="8633b-118">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="8633b-118">dec 02 2016</span></span>
    
- <span data-ttu-id="8633b-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="8633b-119">12/2/2016</span></span>
    
- <span data-ttu-id="8633b-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="8633b-120">12/02/16</span></span>
    
- <span data-ttu-id="8633b-121">Dez-2-2016</span><span class="sxs-lookup"><span data-stu-id="8633b-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="8633b-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="8633b-122">12-2-16</span></span>
    
<span data-ttu-id="8633b-123">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="8633b-123">Accepted month names:</span></span>
  
- <span data-ttu-id="8633b-124">Englisch</span><span class="sxs-lookup"><span data-stu-id="8633b-124">English</span></span>
    
  - <span data-ttu-id="8633b-125">Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="8633b-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="8633b-126">Jan. Feb. Mär. Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span><span class="sxs-lookup"><span data-stu-id="8633b-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="8633b-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="8633b-127">Func_eu_date</span></span>

<span data-ttu-id="8633b-128">Diese Funktion sucht nach einem Datum in dem Format, das in der EU häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8633b-128">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="8633b-129">(und die meisten Orte außerhalb der USA).</span><span class="sxs-lookup"><span data-stu-id="8633b-129">(and most places outside the U.S.).</span></span> <span data-ttu-id="8633b-130">Dies umfasst die Formate "Tag/Monat/Jahr", "Tag-Monat-Jahr" und "Tag Monat Jahr".</span><span class="sxs-lookup"><span data-stu-id="8633b-130">This includes the formats "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="8633b-131">Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="8633b-131">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="8633b-132">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="8633b-132">Examples:</span></span>
  
- <span data-ttu-id="8633b-133">2. Dez. 2016</span><span class="sxs-lookup"><span data-stu-id="8633b-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="8633b-134">02 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="8633b-134">02 dec 2016</span></span>
    
- <span data-ttu-id="8633b-135">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="8633b-135">2 Dec 16</span></span>
    
- <span data-ttu-id="8633b-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="8633b-136">2/12/2016</span></span>
    
- <span data-ttu-id="8633b-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="8633b-137">02/12/16</span></span>
    
- <span data-ttu-id="8633b-138">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="8633b-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="8633b-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="8633b-139">2-12-16</span></span>
    
<span data-ttu-id="8633b-140">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="8633b-140">Accepted month names:</span></span>
  
- <span data-ttu-id="8633b-141">Englisch</span><span class="sxs-lookup"><span data-stu-id="8633b-141">English</span></span>
    
  - <span data-ttu-id="8633b-142">Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="8633b-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="8633b-143">Jan. Feb. Mär. Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span><span class="sxs-lookup"><span data-stu-id="8633b-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="8633b-144">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="8633b-144">Dutch</span></span>
    
  - <span data-ttu-id="8633b-145">Januari, februari, maart, April, Mei, Juni, Juli, Augustus, September, ocktober, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="8633b-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="8633b-146">Jan Feb maart Apr Mei Jun Jul Aug Sep Sept Oct Okt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="8633b-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="8633b-147">Französisch</span><span class="sxs-lookup"><span data-stu-id="8633b-147">French</span></span>
    
  - <span data-ttu-id="8633b-148">janvier, février, Mars, Avril, Mai, Juni juillet, août, September, Oktober, Novembre, Novembre</span><span class="sxs-lookup"><span data-stu-id="8633b-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="8633b-149">janv.</span><span class="sxs-lookup"><span data-stu-id="8633b-149">janv.</span></span> <span data-ttu-id="8633b-150">févr.</span><span class="sxs-lookup"><span data-stu-id="8633b-150">févr.</span></span> <span data-ttu-id="8633b-151">Mars Avril Mai Juni juil.</span><span class="sxs-lookup"><span data-stu-id="8633b-151">mars avril mai juin juil.</span></span> <span data-ttu-id="8633b-152">août Sept.</span><span class="sxs-lookup"><span data-stu-id="8633b-152">août sept.</span></span> <span data-ttu-id="8633b-153">OAT.</span><span class="sxs-lookup"><span data-stu-id="8633b-153">oct.</span></span> <span data-ttu-id="8633b-154">Nov.</span><span class="sxs-lookup"><span data-stu-id="8633b-154">nov.</span></span> <span data-ttu-id="8633b-155">déc.</span><span class="sxs-lookup"><span data-stu-id="8633b-155">déc.</span></span>
    
- <span data-ttu-id="8633b-156">Deutsch</span><span class="sxs-lookup"><span data-stu-id="8633b-156">German</span></span>
    
  - <span data-ttu-id="8633b-157">Januar, Februar, März, April, Mai, Juni Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="8633b-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="8633b-158">Jan./Jän.</span><span class="sxs-lookup"><span data-stu-id="8633b-158">Jan./Jän.</span></span> <span data-ttu-id="8633b-159">Februar März Apr. Mai Juni Juli Aug. Sept. Okt.</span><span class="sxs-lookup"><span data-stu-id="8633b-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="8633b-160">Nov. Dez.</span><span class="sxs-lookup"><span data-stu-id="8633b-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="8633b-161">Italienisch</span><span class="sxs-lookup"><span data-stu-id="8633b-161">Italian</span></span>
    
  - <span data-ttu-id="8633b-162">gennaio, febbraio, Marzo, Aprile, Maggio, Juni, Juli, Agosto, Settembre, ottobre, Novembre, Dezember</span><span class="sxs-lookup"><span data-stu-id="8633b-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="8633b-163">Genn.</span><span class="sxs-lookup"><span data-stu-id="8633b-163">genn.</span></span> <span data-ttu-id="8633b-164">febbr.</span><span class="sxs-lookup"><span data-stu-id="8633b-164">febbr.</span></span> <span data-ttu-id="8633b-165">Mrz.</span><span class="sxs-lookup"><span data-stu-id="8633b-165">mar.</span></span> <span data-ttu-id="8633b-166">Apr.</span><span class="sxs-lookup"><span data-stu-id="8633b-166">apr.</span></span> <span data-ttu-id="8633b-167">Magg.</span><span class="sxs-lookup"><span data-stu-id="8633b-167">magg.</span></span> <span data-ttu-id="8633b-168">Juni Juli AG.</span><span class="sxs-lookup"><span data-stu-id="8633b-168">giugno luglio ag.</span></span> <span data-ttu-id="8633b-169">Sett.</span><span class="sxs-lookup"><span data-stu-id="8633b-169">sett.</span></span> <span data-ttu-id="8633b-170">Ott.</span><span class="sxs-lookup"><span data-stu-id="8633b-170">ott.</span></span> <span data-ttu-id="8633b-171">Nov.</span><span class="sxs-lookup"><span data-stu-id="8633b-171">nov.</span></span> <span data-ttu-id="8633b-172">DIC.</span><span class="sxs-lookup"><span data-stu-id="8633b-172">dic.</span></span>
    
- <span data-ttu-id="8633b-173">Portugiesisch</span><span class="sxs-lookup"><span data-stu-id="8633b-173">Portuguese</span></span>
    
  - <span data-ttu-id="8633b-174">Janeiro, Fevereiro, Março, Marco, Abril, Maio, Junho, Julho, Agosto, Setembro, Outubro, Novembro, Dezembro</span><span class="sxs-lookup"><span data-stu-id="8633b-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="8633b-175">Jan FEV Mär ABR Mai Jun Jul ago festgelegt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="8633b-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="8633b-176">Spanisch</span><span class="sxs-lookup"><span data-stu-id="8633b-176">Spanish</span></span>
    
  - <span data-ttu-id="8633b-177">enero, Febrero, Marzo, Abril, Mayo, junio, Julio, Agosto, Septiembre, Octubre, Noviembre, Diciembre</span><span class="sxs-lookup"><span data-stu-id="8633b-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="8633b-178">enero Feb.</span><span class="sxs-lookup"><span data-stu-id="8633b-178">enero feb.</span></span> <span data-ttu-id="8633b-179">Marzo-ABR.</span><span class="sxs-lookup"><span data-stu-id="8633b-179">marzo abr.</span></span> <span data-ttu-id="8633b-180">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="8633b-180">mayo jun.</span></span> <span data-ttu-id="8633b-181">Juli.</span><span class="sxs-lookup"><span data-stu-id="8633b-181">jul.</span></span> <span data-ttu-id="8633b-182">Agosto Sept./Set.</span><span class="sxs-lookup"><span data-stu-id="8633b-182">agosto sept./set.</span></span> <span data-ttu-id="8633b-183">OAT.</span><span class="sxs-lookup"><span data-stu-id="8633b-183">oct.</span></span> <span data-ttu-id="8633b-184">Nov.</span><span class="sxs-lookup"><span data-stu-id="8633b-184">nov.</span></span> <span data-ttu-id="8633b-185">DIC.</span><span class="sxs-lookup"><span data-stu-id="8633b-185">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="8633b-186">Func_eu_date1 (veraltet)</span><span class="sxs-lookup"><span data-stu-id="8633b-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="8633b-187">Diese Funktion ist veraltet, da Sie nur portugiesische Monatsnamen unterstützt, die nun in der `Func_eu_date` obigen Funktion enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8633b-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="8633b-188">Diese Funktion sucht nach einem Datum in dem Format, das in Portugiesisch häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8633b-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="8633b-189">Das Format für diese Funktion ist identisch `Func_eu_date`mit der Unterschiede nur in der verwendeten Sprache.</span><span class="sxs-lookup"><span data-stu-id="8633b-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="8633b-190">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="8633b-190">Examples:</span></span>
  
- <span data-ttu-id="8633b-191">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="8633b-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="8633b-192">02 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="8633b-192">02 dez 2016</span></span>
    
- <span data-ttu-id="8633b-193">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="8633b-193">2 Dez 16</span></span>
    
- <span data-ttu-id="8633b-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="8633b-194">2/12/2016</span></span>
    
- <span data-ttu-id="8633b-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="8633b-195">02/12/16</span></span>
    
- <span data-ttu-id="8633b-196">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="8633b-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="8633b-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="8633b-197">2-12-16</span></span>
    
<span data-ttu-id="8633b-198">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="8633b-198">Accepted month names:</span></span>
  
- <span data-ttu-id="8633b-199">Portugiesisch</span><span class="sxs-lookup"><span data-stu-id="8633b-199">Portuguese</span></span>
    
  - <span data-ttu-id="8633b-200">Janeiro, Fevereiro, Março, Marco, Abril, Maio, Junho, Julho, Agosto, Setembro, Outubro, Novembro, Dezembro</span><span class="sxs-lookup"><span data-stu-id="8633b-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="8633b-201">Jan FEV Mär ABR Mai Jun Jul ago festgelegt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="8633b-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="8633b-202">Func_eu_date2 (veraltet)</span><span class="sxs-lookup"><span data-stu-id="8633b-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="8633b-203">Diese Funktion ist veraltet, da nur niederländische Monatsnamen unterstützt werden, die jetzt in der `Func_eu_date` obigen Funktion enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8633b-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="8633b-204">Diese Funktion sucht nach einem Datum in dem Format, das in Niederländisch häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8633b-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="8633b-205">Das Format für diese Funktion ist identisch `Func_eu_date`mit der Unterschiede nur in der verwendeten Sprache.</span><span class="sxs-lookup"><span data-stu-id="8633b-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="8633b-206">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="8633b-206">Examples:</span></span>
  
- <span data-ttu-id="8633b-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="8633b-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="8633b-208">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="8633b-208">02 mei 2016</span></span>
    
- <span data-ttu-id="8633b-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="8633b-209">2 Mei 16</span></span>
    
- <span data-ttu-id="8633b-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="8633b-210">2/12/2016</span></span>
    
- <span data-ttu-id="8633b-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="8633b-211">02/12/16</span></span>
    
- <span data-ttu-id="8633b-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="8633b-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="8633b-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="8633b-213">2-12-16</span></span>
    
<span data-ttu-id="8633b-214">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="8633b-214">Accepted month names:</span></span>
  
- <span data-ttu-id="8633b-215">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="8633b-215">Dutch</span></span>
    
  - <span data-ttu-id="8633b-216">Januari, februari, maart, April, Mei, Juni, Juli, Augustus, September, ocktober, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="8633b-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="8633b-217">Jan Feb maart Apr Mei Jun Jul Aug Sep Sept Oct Okt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="8633b-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="8633b-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="8633b-218">Func_expiration_date</span></span>

<span data-ttu-id="8633b-219">Diese Funktion sucht nach einem Datum in den Formaten, die häufig von Kredit-und Debitkarten verwendet werden, wodurch Tage zugunsten von Monaten ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8633b-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="8633b-220">Mit dieser Funktion werden Datumsangaben im Format "month/year", "month-year", "[Month Name] Year" und "[month Kürzel] Year" abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="8633b-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="8633b-221">Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="8633b-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="8633b-222">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="8633b-222">Examples:</span></span>
  
- <span data-ttu-id="8633b-223">MM/jj--zum Beispiel 01/11 oder 1/11</span><span class="sxs-lookup"><span data-stu-id="8633b-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="8633b-224">MM/jjjj--zum Beispiel 01/2011 oder 1/2011</span><span class="sxs-lookup"><span data-stu-id="8633b-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="8633b-225">MM-jj--zum Beispiel 01-22 oder 1-11</span><span class="sxs-lookup"><span data-stu-id="8633b-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="8633b-226">MM-yyyy--zum Beispiel 01-2000 oder 1-2000</span><span class="sxs-lookup"><span data-stu-id="8633b-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="8633b-227">Die folgenden Formate unterstützen JJ oder yyyy:</span><span class="sxs-lookup"><span data-stu-id="8633b-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="8633b-228">Monat-yyyy--zum Beispiel. Jan-2010 oder Januar-2010 oder Jan-10 oder Januar-10</span><span class="sxs-lookup"><span data-stu-id="8633b-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="8633b-229">Monat yyyy--zum Beispiel "Januar 2010" oder "Jan 2010" oder "Januar 10" oder "Jan 10"</span><span class="sxs-lookup"><span data-stu-id="8633b-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="8633b-230">Monatjjjj--beispielsweise "january2010" oder "Jan2010" oder "january10" oder "Jan10"</span><span class="sxs-lookup"><span data-stu-id="8633b-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="8633b-231">Monat/JJJJ--zum Beispiel "Januar/2010" oder "Jan/2010" oder "Januar/10" oder "Jan/10"</span><span class="sxs-lookup"><span data-stu-id="8633b-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="8633b-232">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="8633b-232">Accepted month names:</span></span>
  
- <span data-ttu-id="8633b-233">Englisch</span><span class="sxs-lookup"><span data-stu-id="8633b-233">English</span></span>
    
  - <span data-ttu-id="8633b-234">Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="8633b-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="8633b-235">Jan Feb Mär Apr Mai Juni Juli Aug Sept Okt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="8633b-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="8633b-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="8633b-236">Func_us_address</span></span>

<span data-ttu-id="8633b-237">Diese Funktion sucht nach einem US-Bundesland Namen oder einer postalischen Abkürzung, gefolgt von einer gültigen Postleitzahl, genauso wie Sie in Postadressen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8633b-237">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses.</span></span> <span data-ttu-id="8633b-238">Die Postleitzahl muss einer der korrekten Postleitzahlen sein, die dem US-Bundesland Namen oder der Abkürzung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8633b-238">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="8633b-239">Der US-Bundesland Name und die Postleitzahl können nicht durch Interpunktion oder Buchstaben getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="8633b-239">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="8633b-240">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="8633b-240">Examples:</span></span>
  
- <span data-ttu-id="8633b-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="8633b-241">Washington 98052</span></span>
    
- <span data-ttu-id="8633b-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="8633b-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="8633b-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="8633b-243">WA 98052</span></span>
    
- <span data-ttu-id="8633b-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="8633b-244">WA 98052-9998</span></span>
    

