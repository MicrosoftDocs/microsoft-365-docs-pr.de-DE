---
title: 'Referenz: Richtlinientipps zur Verhinderung von Datenverlust (Data Loss Prevention, DLP)'
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: Hier erfahren Sie, wie Sie einer Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) einen Benutzer benachrichtigen, dass er mit Inhalten arbeitet, die mit einer DLP-Richtlinie in Konflikt stehen.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 0c42569da3fcac40d3121a59f7dc004f25dd3f74
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086759"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="ecab0-103">Referenz: Richtlinientipps zur Verhinderung von Datenverlust (Data Loss Prevention, DLP)</span><span class="sxs-lookup"><span data-stu-id="ecab0-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="ecab0-104">DLP-Richtlinientipps in Outlook Web Access werden für alle Bedingungen, Ausnahmen und Aktionen unterstützt, die für Exchange Arbeitsauslastung in einer DLP-Richtlinie gelten, mit Ausnahme der folgenden:</span><span class="sxs-lookup"><span data-stu-id="ecab0-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="ecab0-105">**Bedingungen:**</span><span class="sxs-lookup"><span data-stu-id="ecab0-105">**Conditions:**</span></span>

- <span data-ttu-id="ecab0-106">Sender Is</span><span class="sxs-lookup"><span data-stu-id="ecab0-106">Sender Is</span></span>
- <span data-ttu-id="ecab0-107">Absenderdomäne ist</span><span class="sxs-lookup"><span data-stu-id="ecab0-107">Sender Domain Is</span></span>
- <span data-ttu-id="ecab0-108">Recipient ist Mitglied von</span><span class="sxs-lookup"><span data-stu-id="ecab0-108">Recipient is a member of</span></span>
- <span data-ttu-id="ecab0-109">Kopfzeile enthält Wörter oder Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ecab0-109">Header contains words or phrases</span></span>
- <span data-ttu-id="ecab0-110">Kopfzeile entspricht Mustern</span><span class="sxs-lookup"><span data-stu-id="ecab0-110">Header matches patterns</span></span>
- <span data-ttu-id="ecab0-111">Dokumentgröße gleich oder größer als</span><span class="sxs-lookup"><span data-stu-id="ecab0-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="ecab0-112">Nachrichtentyp ist</span><span class="sxs-lookup"><span data-stu-id="ecab0-112">Message type is</span></span>
- <span data-ttu-id="ecab0-113">Die Wichtigkeit der Nachricht ist</span><span class="sxs-lookup"><span data-stu-id="ecab0-113">Message importance is</span></span>
- <span data-ttu-id="ecab0-114">Inhaltszeichensatz enthält Wörter</span><span class="sxs-lookup"><span data-stu-id="ecab0-114">Content character set contains words</span></span>
- <span data-ttu-id="ecab0-115">Betreff oder Textkörper enthält Wörter oder Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ecab0-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="ecab0-116">Betreff oder Textkörper entspricht Mustern</span><span class="sxs-lookup"><span data-stu-id="ecab0-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="ecab0-117">Inhaltszeichensatz enthält Wörter</span><span class="sxs-lookup"><span data-stu-id="ecab0-117">Content character set contains words</span></span>
- <span data-ttu-id="ecab0-118">Inhalt wird von empfangen</span><span class="sxs-lookup"><span data-stu-id="ecab0-118">Content is received from</span></span>
- <span data-ttu-id="ecab0-119">Hat absender den Richtlinientipp außer Kraft gesetzt</span><span class="sxs-lookup"><span data-stu-id="ecab0-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="ecab0-120">Nachrichtengröße gleich oder größer als</span><span class="sxs-lookup"><span data-stu-id="ecab0-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="ecab0-121">Sender AD-Attribut enthält Wörter oder Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ecab0-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="ecab0-122">Sender AD-Attribut entspricht Mustern</span><span class="sxs-lookup"><span data-stu-id="ecab0-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="ecab0-123">Dokumentinhalt enthält Wörter oder Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ecab0-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="ecab0-124">Dokumentinhalt entspricht Mustern</span><span class="sxs-lookup"><span data-stu-id="ecab0-124">Document content matches patterns</span></span>

<span data-ttu-id="ecab0-125">**Aktionen:**</span><span class="sxs-lookup"><span data-stu-id="ecab0-125">**Actions:**</span></span>

- <span data-ttu-id="ecab0-126">Weiterleiten der Nachricht zur Genehmigung an den Vorgesetzten des Absenders</span><span class="sxs-lookup"><span data-stu-id="ecab0-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="ecab0-127">Weiterleiten der Nachricht zur Genehmigung an bestimmte genehmigende Benutzer</span><span class="sxs-lookup"><span data-stu-id="ecab0-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="ecab0-128">Umleiten der Nachricht an bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="ecab0-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="ecab0-129">Hinzufügen von Empfängern zum Feld An</span><span class="sxs-lookup"><span data-stu-id="ecab0-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="ecab0-130">Hinzufügen von Empfängern zum Cc-Feld</span><span class="sxs-lookup"><span data-stu-id="ecab0-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="ecab0-131">Hinzufügen von Empfängern zum Bcc-Feld</span><span class="sxs-lookup"><span data-stu-id="ecab0-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="ecab0-132">Hinzufügen des Vorgesetzten des Absenders als Empfänger</span><span class="sxs-lookup"><span data-stu-id="ecab0-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="ecab0-133">Hinzufügen eines HTML-Haftungsausschlusses</span><span class="sxs-lookup"><span data-stu-id="ecab0-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="ecab0-134">Vorausgeöffneter E-Mail-Betreff</span><span class="sxs-lookup"><span data-stu-id="ecab0-134">Prepend email subject</span></span>
- <span data-ttu-id="ecab0-135">Entfernen von O365-Nachrichtenverschlüsselung und -rechteschutz</span><span class="sxs-lookup"><span data-stu-id="ecab0-135">Remove O365 Message Encryption and rights protection</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="ecab0-136">Outlook 2013 und höher unterstützt das Anzeigen von Richtlinientipps für nur einige Bedingungen und Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="ecab0-136">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="ecab0-137">Derzeit unterstützt Outlook 2013 und höher das Anzeigen von Richtlinientipps für Richtlinien, die abgesehen von den unten genannten Bedingungen und entsprechenden Ausnahmen keine Bedingung oder Ausnahme enthalten:</span><span class="sxs-lookup"><span data-stu-id="ecab0-137">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="ecab0-138">Inhalt enthält (funktioniert nur für Typen vertraulicher Informationen.</span><span class="sxs-lookup"><span data-stu-id="ecab0-138">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="ecab0-139">Vertraulichkeitsbezeichnungen werden nicht unterstützt)</span><span class="sxs-lookup"><span data-stu-id="ecab0-139">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="ecab0-140">Inhalt wird freigegeben</span><span class="sxs-lookup"><span data-stu-id="ecab0-140">Content is shared</span></span>

<span data-ttu-id="ecab0-141">Beachten Sie, dass alle Bedingungen für E-Mails funktionieren, die in Outlook-Client-App verfasst wurden, wo sie mit Inhalten übereinstimmen und Schutzmaßnahmen für Inhalte erzwingen.</span><span class="sxs-lookup"><span data-stu-id="ecab0-141">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="ecab0-142">Das Anzeigen von Richtlinientipps für Benutzer wird jedoch für bedingungen, die abgesehen von den oben genannten bedingungen verwendet werden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ecab0-142">However, showing policy tips to users is not supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="ecab0-143">Outlook 2013 und höher und Office-Apps auf Desktop unterstützen Richtlinientipps für nur einige Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="ecab0-143">Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="ecab0-144">Die Liste der sofort verwendeten Typen vertraulicher Informationen, die für die Anzeige von DLP-Richtlinientipps in Outlook on Desktop (2013 und höher) und Office-Apps (Word, Excel, PowerPoint) auf Desktop erkannt werden, sind die folgenden:</span><span class="sxs-lookup"><span data-stu-id="ecab0-144">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) and Office apps (Word, Excel, PowerPoint) on Desktop are the following :</span></span>

- <span data-ttu-id="ecab0-145">ABA Routing Number (US-Bankleitzahl)</span><span class="sxs-lookup"><span data-stu-id="ecab0-145">ABA Routing Number</span></span>
- <span data-ttu-id="ecab0-146">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-146">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="ecab0-147">Australische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-147">Australia Bank Account Number</span></span>
- <span data-ttu-id="ecab0-148">Australische Medical Account-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-148">Australia Medical Account Number</span></span>
- <span data-ttu-id="ecab0-149">Australische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-149">Australia Passport Number</span></span>
- <span data-ttu-id="ecab0-150">Australische Steuernummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-150">Australia Tax File Number</span></span>
- <span data-ttu-id="ecab0-151">Azure DocumentDB-Authentifizierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="ecab0-151">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="ecab0-152">Azure IAAS Database Connection String und Azure SQL Connection String</span><span class="sxs-lookup"><span data-stu-id="ecab0-152">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="ecab0-153">Azure IoT Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ecab0-153">Azure IoT Connection String</span></span>  
- <span data-ttu-id="ecab0-154">Azure Publish Setting Password</span><span class="sxs-lookup"><span data-stu-id="ecab0-154">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="ecab0-155">Azure Redis Cache Connection String</span><span class="sxs-lookup"><span data-stu-id="ecab0-155">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="ecab0-156">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="ecab0-156">Azure SAS</span></span>  
- <span data-ttu-id="ecab0-157">Azure Service Bus-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ecab0-157">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="ecab0-158">Azure Storage Kontoschlüssel</span><span class="sxs-lookup"><span data-stu-id="ecab0-158">Azure Storage Account Key</span></span>  
- <span data-ttu-id="ecab0-159">Azure Storage Kontoschlüssel (Generisch)</span><span class="sxs-lookup"><span data-stu-id="ecab0-159">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="ecab0-160">Nationale belgische Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-160">Belgium National Number</span></span>
- <span data-ttu-id="ecab0-161">Brazil CPF Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-161">Brazil CPF Number</span></span>
- <span data-ttu-id="ecab0-162">Brasilien – Juristische Personennummer (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="ecab0-162">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="ecab0-163">	Brasilien – Personalausweis (RG)</span><span class="sxs-lookup"><span data-stu-id="ecab0-163">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="ecab0-164">Kanadische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-164">Canada Bank Account Number</span></span>
- <span data-ttu-id="ecab0-165">Kanadische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-165">Canada Driver's License Number</span></span>
- <span data-ttu-id="ecab0-166">Kanadische Health Service-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-166">Canada Health Service Number</span></span>
- <span data-ttu-id="ecab0-167">Kanadische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-167">Canada Passport Number</span></span>
- <span data-ttu-id="ecab0-168">Kanadische Personal Health Identification-Nummer (PHIN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-168">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="ecab0-169">Kanadische Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-169">Canada Social Insurance Number</span></span>
- <span data-ttu-id="ecab0-170">	Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-170">Chile Identity Card Number</span></span>
- <span data-ttu-id="ecab0-171">	China (PRC) – Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-171">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="ecab0-172">Kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-172">Credit Card Number</span></span>
- <span data-ttu-id="ecab0-173">Kroatische ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-173">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="ecab0-174">Kroatische persönliche ID-Nummer (OIB)</span><span class="sxs-lookup"><span data-stu-id="ecab0-174">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="ecab0-175">Tschechische Persönliche Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-175">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="ecab0-176">Dänische persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-176">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="ecab0-177">Drug Enforcement Agency (DEA)-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-177">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="ecab0-178">EU-Debitkartennummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-178">EU Debit Card Number</span></span>
- <span data-ttu-id="ecab0-179">EU-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-179">EU Driver's License Number</span></span>  
- <span data-ttu-id="ecab0-180">Nationale EU-Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-180">EU National Identification Number</span></span>  
- <span data-ttu-id="ecab0-181">EU-Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-181">EU Passport Number</span></span>  
- <span data-ttu-id="ecab0-182">EU-Sozialversicherungsnummer (SSN) oder Äquivalent-ID</span><span class="sxs-lookup"><span data-stu-id="ecab0-182">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="ecab0-183">EU Tax Identification Number (TIN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-183">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="ecab0-184">Nationale finnische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-184">Finland National ID</span></span>
- <span data-ttu-id="ecab0-185">Finnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-185">Finland Passport Number</span></span>
- <span data-ttu-id="ecab0-186">Französische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-186">France Driver's License Number</span></span>
- <span data-ttu-id="ecab0-187">Französischer Personalausweis (Carte Nationale d'Identité, CNI)</span><span class="sxs-lookup"><span data-stu-id="ecab0-187">France National ID Card (CNI)</span></span>
- <span data-ttu-id="ecab0-188">Französische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-188">France Passport Number</span></span>
- <span data-ttu-id="ecab0-189">Französische Sozialversicherungsnummer (INSEE)</span><span class="sxs-lookup"><span data-stu-id="ecab0-189">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="ecab0-190">Deutsche Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-190">German Driver's License Number</span></span>
- <span data-ttu-id="ecab0-191">Deutsche Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-191">German Passport Number</span></span>
- <span data-ttu-id="ecab0-192">Deutsche Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-192">Germany Identity Card Number</span></span>
- <span data-ttu-id="ecab0-193">Nationale griechische ID-Karte</span><span class="sxs-lookup"><span data-stu-id="ecab0-193">Greece National ID Card</span></span>  
- <span data-ttu-id="ecab0-194">Hongkong (HKID) - Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-194">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="ecab0-195">Indien – Permanente Kontonummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-195">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="ecab0-196">Indien - Eindeutige Identifikationsnummer (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="ecab0-196">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="ecab0-197">Indonesien – Perosonalausweisnummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="ecab0-197">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="ecab0-198">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-198">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="ecab0-199">International Classification of Diseases (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="ecab0-199">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="ecab0-200">International Classification of Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="ecab0-200">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="ecab0-201">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="ecab0-201">IP Address</span></span>
- <span data-ttu-id="ecab0-202">Irische PPS-Nummer (Personal Public Service)</span><span class="sxs-lookup"><span data-stu-id="ecab0-202">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="ecab0-203">Israelische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-203">Israel Bank Account Number</span></span>
- <span data-ttu-id="ecab0-204">Israelische Ausweis-ID</span><span class="sxs-lookup"><span data-stu-id="ecab0-204">Israel National ID</span></span>
- <span data-ttu-id="ecab0-205">Italienische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-205">Italy Driver's License Number</span></span>
- <span data-ttu-id="ecab0-206">Japanische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-206">Japan Bank Account Number</span></span>
- <span data-ttu-id="ecab0-207">Japanische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-207">Japan Driver's License Number</span></span>
- <span data-ttu-id="ecab0-208">Japanische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-208">Japan Passport Number</span></span>
- <span data-ttu-id="ecab0-209">Japanische Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-209">Japan Resident Registration Number</span></span>
- <span data-ttu-id="ecab0-210">Japanische Sozialversicherungsnummer (SIN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-210">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="ecab0-211">Japanische Wohnsitzkartennummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-211">Japanese Residence Card Number</span></span>
- <span data-ttu-id="ecab0-212">Malaysia Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-212">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="ecab0-213">Nummer des niederländischen Citizen's Service (BSN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-213">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="ecab0-214">Neuseeländische Gesundheitsministeriumsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-214">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="ecab0-215">Norwegische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-215">Norway Identity Number</span></span>  
- <span data-ttu-id="ecab0-216">Philippinen – Vereinheitlichte Mehrzweck-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-216">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="ecab0-217">Polnische Identitätskarte</span><span class="sxs-lookup"><span data-stu-id="ecab0-217">Poland Identity Card</span></span>
- <span data-ttu-id="ecab0-218">Nationale polnische ID-Nummer (PESEL)</span><span class="sxs-lookup"><span data-stu-id="ecab0-218">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="ecab0-219">Polnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-219">Poland Passport</span></span>
- <span data-ttu-id="ecab0-220">Portugiesische ID-Kartennummer (Citizen Card)</span><span class="sxs-lookup"><span data-stu-id="ecab0-220">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="ecab0-221">Saudi-Arabische Ausweisnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-221">Saudi Arabia National ID</span></span>
- <span data-ttu-id="ecab0-222">Singapur – National Registration Identity Card-Nummer (NRIC)</span><span class="sxs-lookup"><span data-stu-id="ecab0-222">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="ecab0-223">Südafrika – Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-223">South Africa Identification Number</span></span>  
- <span data-ttu-id="ecab0-224">Südkorea – Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-224">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="ecab0-225">Spanische Sozialversicherungsnummer (SSN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-225">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="ecab0-226">SQL Server Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ecab0-226">SQL Server Connection String</span></span>  
- <span data-ttu-id="ecab0-227">Nationale schwedische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-227">Sweden National ID</span></span>
- <span data-ttu-id="ecab0-228">Schwedische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-228">Sweden Passport Number</span></span>
- <span data-ttu-id="ecab0-229">SWIFT-Code</span><span class="sxs-lookup"><span data-stu-id="ecab0-229">SWIFT Code</span></span>
- <span data-ttu-id="ecab0-230">Taiwanesicher Personalausweis</span><span class="sxs-lookup"><span data-stu-id="ecab0-230">Taiwan National ID</span></span>
- <span data-ttu-id="ecab0-231">	Taiwan – Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-231">Taiwan Passport Number</span></span>
- <span data-ttu-id="ecab0-232">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="ecab0-232">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="ecab0-233">Thai Population Identification Code</span><span class="sxs-lookup"><span data-stu-id="ecab0-233">Thai Population Identification Code</span></span>
- <span data-ttu-id="ecab0-234">Nationale Identifikationsnummer der Türkei</span><span class="sxs-lookup"><span data-stu-id="ecab0-234">Turkish National Identification number</span></span>
- <span data-ttu-id="ecab0-p103">Vereinigtes Königreich – Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="ecab0-p104">Vereinigtes Königreich – Wählerverzeichnisnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="ecab0-p105">UK-Gesundheitsdienstnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="ecab0-p106">UK-Sozialversicherungsnummer (National Insurance Number, NINO)</span><span class="sxs-lookup"><span data-stu-id="ecab0-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="ecab0-p107">US-amerikanische/britische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-p107">U.S. / U.K. Passport Number</span></span>
- <span data-ttu-id="ecab0-245">US-Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-245">U.S. Bank Account Number</span></span>
- <span data-ttu-id="ecab0-246">US-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-246">U.S. Driver's License Number</span></span>
- <span data-ttu-id="ecab0-247">US-Steueridentifikationsnummer (ITIN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-247">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="ecab0-248">US-Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-248">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="ecab0-249">Beachten Sie, dass benutzerdefinierte Typen vertraulicher Informationen zusätzlich zu den oben genannten typen für vertrauliche Informationen auch für DLP-Richtlinientipps unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="ecab0-249">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="ecab0-250">Verhinderung von Datenverlust auf Endpunktgeräten unterstützt Richtlinientipps nur für einige typen von vertraulichen Informationen</span><span class="sxs-lookup"><span data-stu-id="ecab0-250">Data Loss Prevention on endpoint devices supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="ecab0-251">Die Liste der sofort verwendeten Typen vertraulicher Informationen, die in Dokumenten erkannt werden, die sich auf Endpunktgeräten befinden, sind folgende:</span><span class="sxs-lookup"><span data-stu-id="ecab0-251">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="ecab0-252">ABA Routing Number (US-Bankleitzahl)</span><span class="sxs-lookup"><span data-stu-id="ecab0-252">ABA Routing Number</span></span> 
- <span data-ttu-id="ecab0-253">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-253">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="ecab0-254">Australische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-254">Australia Bank Account Number</span></span> 
- <span data-ttu-id="ecab0-255">Australische Medical Account-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-255">Australia Medical Account Number</span></span> 
- <span data-ttu-id="ecab0-256">Australische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-256">Australia Passport Number</span></span> 
- <span data-ttu-id="ecab0-257">Australische Steuernummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-257">Australia Tax File Number</span></span> 
- <span data-ttu-id="ecab0-258">Australische Geschäftsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-258">Australian Business Number</span></span> 
- <span data-ttu-id="ecab0-259">Australische Firmennummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-259">Australian Company Number</span></span> 
- <span data-ttu-id="ecab0-260">Austria Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-260">Austria Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-261">Austria Identity Card</span><span class="sxs-lookup"><span data-stu-id="ecab0-261">Austria Identity Card</span></span> 
- <span data-ttu-id="ecab0-262">Austria Passport Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-262">Austria Passport Number</span></span> 
- <span data-ttu-id="ecab0-263">Österreich Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-263">Austria Social Security Number</span></span> 
- <span data-ttu-id="ecab0-264">Steueridentifikationsnummer für Österreich</span><span class="sxs-lookup"><span data-stu-id="ecab0-264">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="ecab0-265">Austria Value Added Tax (VAT) Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-265">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="ecab0-266">Azure DocumentDB-Authentifizierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="ecab0-266">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="ecab0-267">Azure IAAS Database Connection String und Azure SQL Connection String</span><span class="sxs-lookup"><span data-stu-id="ecab0-267">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="ecab0-268">Azure IoT Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ecab0-268">Azure IoT Connection String</span></span> 
- <span data-ttu-id="ecab0-269">Azure Publish Setting Password</span><span class="sxs-lookup"><span data-stu-id="ecab0-269">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="ecab0-270">Azure Redis Cache Connection String</span><span class="sxs-lookup"><span data-stu-id="ecab0-270">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="ecab0-271">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="ecab0-271">Azure SAS</span></span> 
- <span data-ttu-id="ecab0-272">Azure Service Bus-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ecab0-272">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="ecab0-273">Azure Storage Kontoschlüssel</span><span class="sxs-lookup"><span data-stu-id="ecab0-273">Azure Storage Account Key</span></span> 
- <span data-ttu-id="ecab0-274">Azure Storage Kontoschlüssel (Generisch)</span><span class="sxs-lookup"><span data-stu-id="ecab0-274">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="ecab0-275">Belgische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-275">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-276">Nationale belgische Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-276">Belgium National Number</span></span> 
- <span data-ttu-id="ecab0-277">Belgische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-277">Belgium Passport Number</span></span> 
- <span data-ttu-id="ecab0-278">Belgische Umsatzsteuernummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-278">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="ecab0-279">Brazil CPF Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-279">Brazil CPF Number</span></span> 
- <span data-ttu-id="ecab0-280">Brasilien – Juristische Personennummer (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="ecab0-280">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="ecab0-281">	Brasilien – Personalausweis (RG)</span><span class="sxs-lookup"><span data-stu-id="ecab0-281">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="ecab0-282">Kennzeichen des Bulgarien-Führerscheins</span><span class="sxs-lookup"><span data-stu-id="ecab0-282">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-283">Bulgarien Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-283">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="ecab0-284">Uniform Civil Number (Bulgarien)</span><span class="sxs-lookup"><span data-stu-id="ecab0-284">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="ecab0-285">Kanadische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-285">Canada Bank Account Number</span></span> 
- <span data-ttu-id="ecab0-286">Kanadische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-286">Canada Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-287">Kanadische Health Service-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-287">Canada Health Service Number</span></span> 
- <span data-ttu-id="ecab0-288">Kanadische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-288">Canada Passport Number</span></span> 
- <span data-ttu-id="ecab0-289">Kanadische Personal Health Identification-Nummer (PHIN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-289">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="ecab0-290">Kanadische Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-290">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="ecab0-291">	Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-291">Chile Identity Card Number</span></span> 
- <span data-ttu-id="ecab0-292">	China (PRC) – Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-292">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="ecab0-293">Kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-293">Credit Card Number</span></span> 
- <span data-ttu-id="ecab0-294">Kroatische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-294">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-295">Kroatische ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-295">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="ecab0-296">Kroatische Nationale ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-296">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="ecab0-297">Kroatische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-297">Croatia Passport Number</span></span> 
- <span data-ttu-id="ecab0-298">Kroatische persönliche ID-Nummer (OIB)</span><span class="sxs-lookup"><span data-stu-id="ecab0-298">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="ecab0-299">CSCAN-AZURE0060 Azure Storage kontosignatur für gemeinsamen Zugriff</span><span class="sxs-lookup"><span data-stu-id="ecab0-299">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="ecab0-300">CSCAN-GENERAL0140 Allgemeiner symmetrischer Schlüssel</span><span class="sxs-lookup"><span data-stu-id="ecab0-300">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="ecab0-301">Zyprische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-301">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-302">Identitätskarte für Zypern</span><span class="sxs-lookup"><span data-stu-id="ecab0-302">Cyprus Identity Card</span></span> 
- <span data-ttu-id="ecab0-303">Reisepassnummer für Zypern</span><span class="sxs-lookup"><span data-stu-id="ecab0-303">Cyprus Passport Number</span></span> 
- <span data-ttu-id="ecab0-304">Steueridentifikationsnummer für Zypern</span><span class="sxs-lookup"><span data-stu-id="ecab0-304">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="ecab0-305">Tschechische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-305">Czech Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-306">Tschechische Persönliche Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-306">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="ecab0-307">Tschechische Republik Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-307">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="ecab0-308">Dänische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-308">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-309">Dänische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-309">Denmark Passport Number</span></span> 
- <span data-ttu-id="ecab0-310">Dänische persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-310">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="ecab0-311">Drug Enforcement Agency (DEA)-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-311">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="ecab0-312">Estonia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-312">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-313">Estonia Passport Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-313">Estonia Passport Number</span></span> 
- <span data-ttu-id="ecab0-314">Estonia Personal Identification Code</span><span class="sxs-lookup"><span data-stu-id="ecab0-314">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="ecab0-315">EU-Debitkartennummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-315">EU Debit Card Number</span></span> 
- <span data-ttu-id="ecab0-316">EU-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-316">EU Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-317">Nationale EU-Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-317">EU National Identification Number</span></span> 
- <span data-ttu-id="ecab0-318">EU-Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-318">EU Passport Number</span></span> 
- <span data-ttu-id="ecab0-319">EU-Sozialversicherungsnummer (SSN) oder Äquivalent-ID</span><span class="sxs-lookup"><span data-stu-id="ecab0-319">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="ecab0-320">EU Tax Identification Number (TIN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-320">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="ecab0-321">Finland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-321">Finland Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-322">Finnland Europäische Krankenversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-322">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="ecab0-323">Nationale finnische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-323">Finland National ID</span></span> 
- <span data-ttu-id="ecab0-324">Finnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-324">Finland Passport Number</span></span> 
- <span data-ttu-id="ecab0-325">Französische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-325">France Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-326">Französische Krankenversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-326">France Health Insurance Number</span></span> 
- <span data-ttu-id="ecab0-327">Französischer Personalausweis (Carte Nationale d'Identité, CNI)</span><span class="sxs-lookup"><span data-stu-id="ecab0-327">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="ecab0-328">Französische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-328">France Passport Number</span></span> 
- <span data-ttu-id="ecab0-329">Französische Sozialversicherungsnummer (INSEE)</span><span class="sxs-lookup"><span data-stu-id="ecab0-329">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="ecab0-330">Französische Steueridentifikationsnummer (numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="ecab0-330">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="ecab0-331">Französische Umsatzsteuernummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-331">France Value Added Tax Number</span></span> 
- <span data-ttu-id="ecab0-332">Deutsche Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-332">German Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-333">Deutsche Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-333">German Passport Number</span></span> 
- <span data-ttu-id="ecab0-334">Deutsche Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-334">Germany Identity Card Number</span></span> 
- <span data-ttu-id="ecab0-335">Deutsche Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-335">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="ecab0-336">Deutsche Umsatzsteuernummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-336">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="ecab0-337">Führerscheinnummer für Griechenland</span><span class="sxs-lookup"><span data-stu-id="ecab0-337">Greece Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-338">Nationale griechische ID-Karte</span><span class="sxs-lookup"><span data-stu-id="ecab0-338">Greece National ID Card</span></span> 
- <span data-ttu-id="ecab0-339">Griechenland Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-339">Greece Passport Number</span></span> 
- <span data-ttu-id="ecab0-340">Griechenland Sozialversicherungsnummer (AMKA)</span><span class="sxs-lookup"><span data-stu-id="ecab0-340">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="ecab0-341">Griechische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-341">Greek Tax identification Number</span></span> 
- <span data-ttu-id="ecab0-342">Hongkong (HKID) - Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-342">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="ecab0-343">Ungarische Sozialversicherungsnummer (TAJ)</span><span class="sxs-lookup"><span data-stu-id="ecab0-343">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="ecab0-344">Mehrwertsteuernummer für Ungarn</span><span class="sxs-lookup"><span data-stu-id="ecab0-344">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="ecab0-345">Kennzeichen des Ungarn-Führerscheins</span><span class="sxs-lookup"><span data-stu-id="ecab0-345">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-346">Ungarn Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-346">Hungary Passport Number</span></span> 
- <span data-ttu-id="ecab0-347">Ungarn Persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-347">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="ecab0-348">Ungarn Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-348">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="ecab0-349">Indien – Permanente Kontonummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-349">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="ecab0-350">Indien - Eindeutige Identifikationsnummer (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="ecab0-350">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="ecab0-351">Indonesien – Perosonalausweisnummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="ecab0-351">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="ecab0-352">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-352">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="ecab0-353">International Classification of Diseases (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="ecab0-353">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="ecab0-354">International Classification of Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="ecab0-354">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="ecab0-355">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="ecab0-355">IP Address</span></span> 
- <span data-ttu-id="ecab0-356">Ireland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-356">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-357">Irland Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-357">Ireland Passport Number</span></span> 
- <span data-ttu-id="ecab0-358">Irische PPS-Nummer (Personal Public Service)</span><span class="sxs-lookup"><span data-stu-id="ecab0-358">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="ecab0-359">Israelische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-359">Israel Bank Account Number</span></span> 
- <span data-ttu-id="ecab0-360">Israelische Ausweis-ID</span><span class="sxs-lookup"><span data-stu-id="ecab0-360">Israel National ID</span></span> 
- <span data-ttu-id="ecab0-361">Italienische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-361">Italy Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-362">Steuercode für Italien</span><span class="sxs-lookup"><span data-stu-id="ecab0-362">Italy Fiscal Code</span></span> 
- <span data-ttu-id="ecab0-363">Italienische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-363">Italy Passport Number</span></span> 
- <span data-ttu-id="ecab0-364">Italienische Mehrwertsteuernummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-364">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="ecab0-365">Japanische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-365">Japan Bank Account Number</span></span> 
- <span data-ttu-id="ecab0-366">Japanische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-366">Japan Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-367">Japanische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-367">Japan Passport Number</span></span> 
- <span data-ttu-id="ecab0-368">Japanische Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-368">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="ecab0-369">Japanische Sozialversicherungsnummer (SIN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-369">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="ecab0-370">Japanische My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="ecab0-370">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="ecab0-371">Japanisch My Number Personal</span><span class="sxs-lookup"><span data-stu-id="ecab0-371">Japanese My Number Personal</span></span> 
- <span data-ttu-id="ecab0-372">Japanische Wohnsitzkartennummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-372">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="ecab0-373">Latvia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-373">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-374">Latvia Passport Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-374">Latvia Passport Number</span></span> 
- <span data-ttu-id="ecab0-375">Persönlichen Code für Lettland</span><span class="sxs-lookup"><span data-stu-id="ecab0-375">Latvia Personal Code</span></span> 
- <span data-ttu-id="ecab0-376">Lizenznummer des Litauen-Führerscheins</span><span class="sxs-lookup"><span data-stu-id="ecab0-376">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-377">Reisepassnummer für Litauen</span><span class="sxs-lookup"><span data-stu-id="ecab0-377">Lithuania Passport Number</span></span> 
- <span data-ttu-id="ecab0-378">Persönlichen Code für Litauen</span><span class="sxs-lookup"><span data-stu-id="ecab0-378">Lithuania Personal Code</span></span> 
- <span data-ttu-id="ecab0-379">LuxemburgEr Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-379">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-380">Nationale Identifikationsnummer (natürliche Personen)</span><span class="sxs-lookup"><span data-stu-id="ecab0-380">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="ecab0-381">Nationale Identifikationsnummer (nicht natürliche Personen)</span><span class="sxs-lookup"><span data-stu-id="ecab0-381">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="ecab0-382">Luxemburg Passport Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-382">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="ecab0-383">Malaysia Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-383">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="ecab0-384">Malta Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-384">Malta Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-385">Malta Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-385">Malta Identity Card Number</span></span> 
- <span data-ttu-id="ecab0-386">Malta Passport Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-386">Malta Passport Number</span></span> 
- <span data-ttu-id="ecab0-387">Malta Steuer-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-387">Malta Tax ID Number</span></span> 
- <span data-ttu-id="ecab0-388">Nummer des niederländischen Citizen's Service (BSN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-388">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="ecab0-389">Niederländische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-389">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-390">Niederländische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-390">Netherlands Passport Number</span></span> 
- <span data-ttu-id="ecab0-391">Niederländische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-391">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="ecab0-392">Niederländische Umsatzsteuernummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-392">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="ecab0-393">Bankkontonummer für Neuseeland</span><span class="sxs-lookup"><span data-stu-id="ecab0-393">New Zealand bank account number</span></span> 
- <span data-ttu-id="ecab0-394">New Zealand Driver License Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-394">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="ecab0-395">New Zealand Inland Revenue Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-395">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="ecab0-396">Neuseeländische Gesundheitsministeriumsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-396">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="ecab0-397">New Zealand Social Welfare Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-397">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="ecab0-398">Norwegische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-398">Norway Identity Number</span></span> 
- <span data-ttu-id="ecab0-399">Philippinen – Vereinheitlichte Mehrzweck-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-399">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="ecab0-400">Polnische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-400">Poland Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-401">Polnische Identitätskarte</span><span class="sxs-lookup"><span data-stu-id="ecab0-401">Poland Identity Card</span></span> 
- <span data-ttu-id="ecab0-402">Nationale polnische ID-Nummer (PESEL)</span><span class="sxs-lookup"><span data-stu-id="ecab0-402">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="ecab0-403">Polnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-403">Poland Passport</span></span> 
- <span data-ttu-id="ecab0-404">Polnische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-404">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="ecab0-405">Polnische REGON-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-405">Polish REGON Number</span></span> 
- <span data-ttu-id="ecab0-406">Portugiesische ID-Kartennummer (Citizen Card)</span><span class="sxs-lookup"><span data-stu-id="ecab0-406">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="ecab0-407">Portugal Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-407">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-408">Portugal Passport Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-408">Portugal Passport Number</span></span> 
- <span data-ttu-id="ecab0-409">Steueridentifikationsnummer für Portugal</span><span class="sxs-lookup"><span data-stu-id="ecab0-409">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="ecab0-410">Romania Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-410">Romania Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-411">Rumänien Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-411">Romania Passport Number</span></span> 
- <span data-ttu-id="ecab0-412">Rumänien – Persönlicher numerischer Code (CNP)</span><span class="sxs-lookup"><span data-stu-id="ecab0-412">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="ecab0-413">Russische Reisepassnummer (Inland)</span><span class="sxs-lookup"><span data-stu-id="ecab0-413">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="ecab0-414">Russische Reisepassnummer (International)</span><span class="sxs-lookup"><span data-stu-id="ecab0-414">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="ecab0-415">Saudi-Arabische Ausweisnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-415">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="ecab0-416">Singapur – National Registration Identity Card-Nummer (NRIC)</span><span class="sxs-lookup"><span data-stu-id="ecab0-416">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="ecab0-417">Slovakia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-417">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-418">Slowakei Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-418">Slovakia Passport Number</span></span> 
- <span data-ttu-id="ecab0-419">Persönliche Nummer der Slowakei</span><span class="sxs-lookup"><span data-stu-id="ecab0-419">Slovakia Personal Number</span></span> 
- <span data-ttu-id="ecab0-420">Slovenia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-420">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-421">Slowenien Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-421">Slovenia Passport Number</span></span> 
- <span data-ttu-id="ecab0-422">Slowenien Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-422">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="ecab0-423">Slowenien Eindeutige Master Citizen Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-423">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="ecab0-424">Südafrika – Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-424">South Africa Identification Number</span></span> 
- <span data-ttu-id="ecab0-425">Südkorea – Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-425">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="ecab0-426">Spanien DNI</span><span class="sxs-lookup"><span data-stu-id="ecab0-426">Spain DNI</span></span> 
- <span data-ttu-id="ecab0-427">Spain Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="ecab0-427">Spain Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-428">Spanische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-428">Spain Passport Number</span></span> 
- <span data-ttu-id="ecab0-429">Spanische Sozialversicherungsnummer (SSN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-429">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="ecab0-430">Spanien Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-430">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="ecab0-431">SQL Server Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ecab0-431">SQL Server Connection String</span></span> 
- <span data-ttu-id="ecab0-432">Schwedische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-432">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-433">Nationale schwedische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-433">Sweden National ID</span></span> 
- <span data-ttu-id="ecab0-434">Schwedische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-434">Sweden Passport Number</span></span> 
- <span data-ttu-id="ecab0-435">Steueridentifikationsnummer für Schweden</span><span class="sxs-lookup"><span data-stu-id="ecab0-435">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="ecab0-436">SWIFT-Code</span><span class="sxs-lookup"><span data-stu-id="ecab0-436">SWIFT Code</span></span> 
- <span data-ttu-id="ecab0-437">Swiss Social Security Number AHV</span><span class="sxs-lookup"><span data-stu-id="ecab0-437">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="ecab0-438">Taiwanesicher Personalausweis</span><span class="sxs-lookup"><span data-stu-id="ecab0-438">Taiwan National ID</span></span> 
- <span data-ttu-id="ecab0-439">	Taiwan – Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-439">Taiwan Passport Number</span></span> 
- <span data-ttu-id="ecab0-440">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="ecab0-440">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="ecab0-441">Thai Population Identification Code</span><span class="sxs-lookup"><span data-stu-id="ecab0-441">Thai Population Identification Code</span></span> 
- <span data-ttu-id="ecab0-442">Nationale Identifikationsnummer der Türkei</span><span class="sxs-lookup"><span data-stu-id="ecab0-442">Turkish National Identification number</span></span> 
- <span data-ttu-id="ecab0-p108">Vereinigtes Königreich – Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-p109">Vereinigtes Königreich – Wählerverzeichnisnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="ecab0-p110">UK-Gesundheitsdienstnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="ecab0-p111">UK-Sozialversicherungsnummer (National Insurance Number, NINO)</span><span class="sxs-lookup"><span data-stu-id="ecab0-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="ecab0-451">Vereinigtes Königreich</span><span class="sxs-lookup"><span data-stu-id="ecab0-451">U.K.</span></span> <span data-ttu-id="ecab0-452">Eindeutige Steuernummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-452">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="ecab0-p113">US-amerikanische/britische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-p113">U.S. / U.K. Passport Number</span></span> 
- <span data-ttu-id="ecab0-455">US-Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-455">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="ecab0-456">US-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-456">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="ecab0-457">US-Steueridentifikationsnummer (ITIN)</span><span class="sxs-lookup"><span data-stu-id="ecab0-457">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="ecab0-458">US-Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="ecab0-458">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="ecab0-459">Ukraine Passport Number (Inland)</span><span class="sxs-lookup"><span data-stu-id="ecab0-459">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="ecab0-460">Ukraine Passport Number (International)</span><span class="sxs-lookup"><span data-stu-id="ecab0-460">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="ecab0-461">Bitte beachten Sie, dass zusätzlich zu den oben genannten sofort verwendeten Typen vertraulicher Informationen auch benutzerdefinierte Typen vertraulicher Informationen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="ecab0-461">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="ecab0-462">Support matrix for DLP policy tips across Microsoft apps</span><span class="sxs-lookup"><span data-stu-id="ecab0-462">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="ecab0-463">**App und Plattform**</span><span class="sxs-lookup"><span data-stu-id="ecab0-463">**App and platform**</span></span>|<span data-ttu-id="ecab0-464">**Unterstützung von DLP-Richtlinientipps**</span><span class="sxs-lookup"><span data-stu-id="ecab0-464">**DLP policy tip support**</span></span>|<span data-ttu-id="ecab0-465">**Unterstützte Typen vertraulicher Informationen**</span><span class="sxs-lookup"><span data-stu-id="ecab0-465">**Sensitive information types supported**</span></span>|<span data-ttu-id="ecab0-466">**Unterstützte Prädikate und Aktionen**</span><span class="sxs-lookup"><span data-stu-id="ecab0-466">**Predicates and actions supported**</span></span>|<span data-ttu-id="ecab0-467">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="ecab0-467">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="ecab0-468">**Outlook WebZugriff**</span><span class="sxs-lookup"><span data-stu-id="ecab0-468">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="ecab0-469">Alle</span><span class="sxs-lookup"><span data-stu-id="ecab0-469">All</span></span>|<span data-ttu-id="ecab0-470">Subset</span><span class="sxs-lookup"><span data-stu-id="ecab0-470">Subset</span></span>|<span data-ttu-id="ecab0-471">Siehe [Hinweise zu Richtlinientipps zur](#data-loss-prevention-policy-tips-reference) Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="ecab0-471">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="ecab0-472">**Outlook Win32 (Outlook 2013 und darüber hinaus)**</span><span class="sxs-lookup"><span data-stu-id="ecab0-472">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="ecab0-473">Subset</span><span class="sxs-lookup"><span data-stu-id="ecab0-473">Subset</span></span>|<span data-ttu-id="ecab0-474">Subset</span><span class="sxs-lookup"><span data-stu-id="ecab0-474">Subset</span></span>|<span data-ttu-id="ecab0-475">Unter [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) und höher werden Richtlinientipps für nur einige Bedingungen und Ausnahmen sowie [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) und höher sowie Office-Apps auf Desktop angezeigt, in denen Richtlinientipps für nur einige typen von vertraulichen Informationen angezeigt werden. Weitere Informationen zur Unterstützung vertraulicher Informationstypen sowie zu DLP-Bedingungen und -Aktionen, die für die Anzeige von Tipps zu DLP-Richtlinien auf Outlook Win32 unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="ecab0-475">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="ecab0-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="ecab0-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="ecab0-477">Keine</span><span class="sxs-lookup"><span data-stu-id="ecab0-477">None</span></span>|<span data-ttu-id="ecab0-478">Keine</span><span class="sxs-lookup"><span data-stu-id="ecab0-478">None</span></span>|<span data-ttu-id="ecab0-479">DLP-Richtlinientipps werden auf mobilen Geräten Outlook unterstützt</span><span class="sxs-lookup"><span data-stu-id="ecab0-479">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="ecab0-480">**Sharepoint Online/One Drive for Business Web Client**</span><span class="sxs-lookup"><span data-stu-id="ecab0-480">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="ecab0-481">Alle</span><span class="sxs-lookup"><span data-stu-id="ecab0-481">All</span></span>|<span data-ttu-id="ecab0-482">Alle SPO/ODB-Prädikate und -Aktionen in DLP</span><span class="sxs-lookup"><span data-stu-id="ecab0-482">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="ecab0-483">**Sharepoint Win32/ One Drive for Business Win32-Client**</span><span class="sxs-lookup"><span data-stu-id="ecab0-483">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="ecab0-484">Keine</span><span class="sxs-lookup"><span data-stu-id="ecab0-484">None</span></span>|<span data-ttu-id="ecab0-485">Keine</span><span class="sxs-lookup"><span data-stu-id="ecab0-485">None</span></span>|<span data-ttu-id="ecab0-486">DLP-Richtlinientipps werden in Sharepoint- oder OneDrive-Client-Apps nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="ecab0-486">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="ecab0-487">**Word, Excel, PowerPoint Web Client**</span><span class="sxs-lookup"><span data-stu-id="ecab0-487">**Word, Excel, PowerPoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="ecab0-488">Alle</span><span class="sxs-lookup"><span data-stu-id="ecab0-488">All</span></span>|<span data-ttu-id="ecab0-489">Alle SPO/ODB-Prädikate und -Aktionen in DLP</span><span class="sxs-lookup"><span data-stu-id="ecab0-489">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="ecab0-490">Der Tipp für die DLP-Richtlinie wird unterstützt, wenn das Dokument in spo- oder ODB-Web-App gehostet wird und die DLP-Richtlinie bereits gestempelt ist.</span><span class="sxs-lookup"><span data-stu-id="ecab0-490">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="ecab0-491">**Word, Excel, PowerPoint Mobile Client**</span><span class="sxs-lookup"><span data-stu-id="ecab0-491">**Word, Excel, PowerPoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="ecab0-492">Keine</span><span class="sxs-lookup"><span data-stu-id="ecab0-492">None</span></span>|<span data-ttu-id="ecab0-493">Keine</span><span class="sxs-lookup"><span data-stu-id="ecab0-493">None</span></span>|<span data-ttu-id="ecab0-494">DLP-Richtlinientipps werden in mobilen Apps für Apps Office.</span><span class="sxs-lookup"><span data-stu-id="ecab0-494">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="ecab0-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="ecab0-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="ecab0-496">Alle</span><span class="sxs-lookup"><span data-stu-id="ecab0-496">All</span></span>|<span data-ttu-id="ecab0-497">Alle Teams in der DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ecab0-497">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="ecab0-498">Richtlinientipps werden angezeigt, wenn eine Nachricht mit "Diese Nachricht wurde gekennzeichnet" gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="ecab0-498">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="ecab0-499">Was kann ich tun?"</span><span class="sxs-lookup"><span data-stu-id="ecab0-499">What can I do?”</span></span> <span data-ttu-id="ecab0-500">Wenn der Benutzer auf den Link klickt, kann er die erkannten Typen vertraulicher Informationen überprüfen und ein Problem außer Kraft setzen oder melden, wenn dies vom Administrator zulässig ist. Beachten Sie, dass keine Richtlinientipps für Dateien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ecab0-500">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="ecab0-501">Wenn der Empfänger versucht, auf das Dokument zu zugreifen, erhält er möglicherweise zugriff verweigert, wenn er nicht zugelassen ist.</span><span class="sxs-lookup"><span data-stu-id="ecab0-501">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="ecab0-502">**Win32-Endpunktgeräte**</span><span class="sxs-lookup"><span data-stu-id="ecab0-502">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="ecab0-503">Subset</span><span class="sxs-lookup"><span data-stu-id="ecab0-503">Subset</span></span>|<span data-ttu-id="ecab0-504">Alle Endpunkt-DLP-Prädikate und -Aktionen in der DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ecab0-504">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="ecab0-505">Weitere [Informationen finden Sie unter Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types.](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="ecab0-505">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="ecab0-506">**Mac-Geräte**</span><span class="sxs-lookup"><span data-stu-id="ecab0-506">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="ecab0-507">Keine</span><span class="sxs-lookup"><span data-stu-id="ecab0-507">None</span></span>|<span data-ttu-id="ecab0-508">Keine</span><span class="sxs-lookup"><span data-stu-id="ecab0-508">None</span></span>|<span data-ttu-id="ecab0-509">Richtlinien zur Verhinderung von Datenverlust sind heute auf Mac-Geräten nicht durchsetzbar</span><span class="sxs-lookup"><span data-stu-id="ecab0-509">Data loss prevention policies are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="ecab0-510">**Cloud-Apps von Drittanbietern**</span><span class="sxs-lookup"><span data-stu-id="ecab0-510">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="ecab0-511">Keine</span><span class="sxs-lookup"><span data-stu-id="ecab0-511">None</span></span>|<span data-ttu-id="ecab0-512">Keine</span><span class="sxs-lookup"><span data-stu-id="ecab0-512">None</span></span>|<span data-ttu-id="ecab0-513">Richtlinientipps zur Verhinderung von Datenverlust werden in Cloud-Apps von Drittanbietern nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ecab0-513">Data Loss Prevention policy tips are not supported on 3rd party cloud apps</span></span>|
|<span data-ttu-id="ecab0-514">**On-Prem**</span><span class="sxs-lookup"><span data-stu-id="ecab0-514">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="ecab0-515">Keine</span><span class="sxs-lookup"><span data-stu-id="ecab0-515">None</span></span>|<span data-ttu-id="ecab0-516">Keine</span><span class="sxs-lookup"><span data-stu-id="ecab0-516">None</span></span>||
|<span data-ttu-id="ecab0-517">**Word, Excel, PowerPoint Win32 Client**</span><span class="sxs-lookup"><span data-stu-id="ecab0-517">**Word, Excel, PowerPoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="ecab0-518">Subset</span><span class="sxs-lookup"><span data-stu-id="ecab0-518">Subset</span></span>|<span data-ttu-id="ecab0-519">Subset</span><span class="sxs-lookup"><span data-stu-id="ecab0-519">Subset</span></span>|<span data-ttu-id="ecab0-520">Unter [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) und höher und Office-Apps auf Desktop finden Sie Richtlinientipps für nur einige typen vertraulicher Informationen für die Liste der unterstützten Typen vertraulicher Informationen.</span><span class="sxs-lookup"><span data-stu-id="ecab0-520">Please see [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for the list of sensitive information types supported</span></span></br></br><span data-ttu-id="ecab0-521">Richtlinientipps für WXP-Client-Apps funktionieren für Dokumente, die auf Sharepoint Online- oder One Drive for Business-Websites gespeichert sind, für alle DLP-Richtlinien, die genau die folgende oder eine Teilmenge von Bedingungen oder Aktionen in der DLP-Richtlinie enthalten:</span><span class="sxs-lookup"><span data-stu-id="ecab0-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="ecab0-522">Inhalt enthält Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="ecab0-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="ecab0-523">Zugriffsbereich (Inhalt wird intern/extern freigegeben)</span><span class="sxs-lookup"><span data-stu-id="ecab0-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="ecab0-524">Benutzer benachrichtigen (Richtlinientipps/Benutzerbenachrichtigungen)</span><span class="sxs-lookup"><span data-stu-id="ecab0-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="ecab0-525">Blockieren von allen</span><span class="sxs-lookup"><span data-stu-id="ecab0-525">Block everyone</span></span></li><li><span data-ttu-id="ecab0-526">Schadensberichte</span><span class="sxs-lookup"><span data-stu-id="ecab0-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="ecab0-527">Wenn eine andere Bedingung oder Aktion vorhanden ist, wird der DLP-Richtlinientipp für diese Richtlinie nicht in den Desktop-Apps von Word, Excel oder PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="ecab0-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span></br><span data-ttu-id="ecab0-528">Weitere Informationen finden Sie unter [Richtlinientipps in Excel, PowerPoint](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) und Word</span><span class="sxs-lookup"><span data-stu-id="ecab0-528">See [Policy tips in Excel, PowerPoint, and Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) for more details</span></span>|
||||||
