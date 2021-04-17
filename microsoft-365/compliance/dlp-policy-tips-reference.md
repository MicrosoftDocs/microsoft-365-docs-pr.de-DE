---
title: Referenz zu Richtlinientipps zur Verhinderung von Datenverlust
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Hier erfahren Sie, wie Sie einer Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) einen Benutzer benachrichtigen, dass er mit Inhalten arbeitet, die mit einer DLP-Richtlinie in Konflikt stehen.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 693f511b6303fb07d393c62efb4a61631b844474
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876810"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="8b69f-103">Referenz zu Richtlinientipps zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="8b69f-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="8b69f-104">DLP-Richtlinientipps in Outlook Web Access werden für alle Bedingungen, Ausnahmen und Aktionen unterstützt, die für die Exchange-Arbeitsauslastung in einer DLP-Richtlinie gelten, mit Ausnahme der folgenden:</span><span class="sxs-lookup"><span data-stu-id="8b69f-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="8b69f-105">**Bedingungen:**</span><span class="sxs-lookup"><span data-stu-id="8b69f-105">**Conditions:**</span></span>

- <span data-ttu-id="8b69f-106">Sender Is</span><span class="sxs-lookup"><span data-stu-id="8b69f-106">Sender Is</span></span>
- <span data-ttu-id="8b69f-107">Absenderdomäne ist</span><span class="sxs-lookup"><span data-stu-id="8b69f-107">Sender Domain Is</span></span>
- <span data-ttu-id="8b69f-108">Recipient ist Mitglied von</span><span class="sxs-lookup"><span data-stu-id="8b69f-108">Recipient is a member of</span></span>
- <span data-ttu-id="8b69f-109">Kopfzeile enthält Wörter oder Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8b69f-109">Header contains words or phrases</span></span>
- <span data-ttu-id="8b69f-110">Kopfzeile entspricht Mustern</span><span class="sxs-lookup"><span data-stu-id="8b69f-110">Header matches patterns</span></span>
- <span data-ttu-id="8b69f-111">Dokumentgröße gleich oder größer als</span><span class="sxs-lookup"><span data-stu-id="8b69f-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="8b69f-112">Nachrichtentyp ist</span><span class="sxs-lookup"><span data-stu-id="8b69f-112">Message type is</span></span>
- <span data-ttu-id="8b69f-113">Die Wichtigkeit der Nachricht ist</span><span class="sxs-lookup"><span data-stu-id="8b69f-113">Message importance is</span></span>
- <span data-ttu-id="8b69f-114">Inhaltszeichensatz enthält Wörter</span><span class="sxs-lookup"><span data-stu-id="8b69f-114">Content character set contains words</span></span>
- <span data-ttu-id="8b69f-115">Betreff oder Textkörper enthält Wörter oder Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8b69f-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="8b69f-116">Betreff oder Textkörper entspricht Mustern</span><span class="sxs-lookup"><span data-stu-id="8b69f-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="8b69f-117">Inhaltszeichensatz enthält Wörter</span><span class="sxs-lookup"><span data-stu-id="8b69f-117">Content character set contains words</span></span>
- <span data-ttu-id="8b69f-118">Inhalt wird von empfangen</span><span class="sxs-lookup"><span data-stu-id="8b69f-118">Content is received from</span></span>
- <span data-ttu-id="8b69f-119">Hat absender den Richtlinientipp außer Kraft gesetzt</span><span class="sxs-lookup"><span data-stu-id="8b69f-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="8b69f-120">Nachrichtengröße gleich oder größer als</span><span class="sxs-lookup"><span data-stu-id="8b69f-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="8b69f-121">Sender AD-Attribut enthält Wörter oder Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8b69f-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="8b69f-122">Sender AD-Attribut entspricht Mustern</span><span class="sxs-lookup"><span data-stu-id="8b69f-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="8b69f-123">Dokumentinhalt enthält Wörter oder Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8b69f-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="8b69f-124">Dokumentinhalt entspricht Mustern</span><span class="sxs-lookup"><span data-stu-id="8b69f-124">Document content matches patterns</span></span>

<span data-ttu-id="8b69f-125">**Aktionen:**</span><span class="sxs-lookup"><span data-stu-id="8b69f-125">**Actions:**</span></span>

- <span data-ttu-id="8b69f-126">Weiterleiten der Nachricht zur Genehmigung an den Vorgesetzten des Absenders</span><span class="sxs-lookup"><span data-stu-id="8b69f-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="8b69f-127">Weiterleiten der Nachricht zur Genehmigung an bestimmte genehmigende Benutzer</span><span class="sxs-lookup"><span data-stu-id="8b69f-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="8b69f-128">Umleiten der Nachricht an bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="8b69f-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="8b69f-129">Hinzufügen von Empfängern zum Feld An</span><span class="sxs-lookup"><span data-stu-id="8b69f-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="8b69f-130">Hinzufügen von Empfängern zum Cc-Feld</span><span class="sxs-lookup"><span data-stu-id="8b69f-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="8b69f-131">Hinzufügen von Empfängern zum Bcc-Feld</span><span class="sxs-lookup"><span data-stu-id="8b69f-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="8b69f-132">Hinzufügen des Vorgesetzten des Absenders als Empfänger</span><span class="sxs-lookup"><span data-stu-id="8b69f-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="8b69f-133">Hinzufügen eines HTML-Haftungsausschlusses</span><span class="sxs-lookup"><span data-stu-id="8b69f-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="8b69f-134">Vorausgeöffneter E-Mail-Betreff</span><span class="sxs-lookup"><span data-stu-id="8b69f-134">Prepend email subject</span></span>
- <span data-ttu-id="8b69f-135">Entfernen von O365-Nachrichtenverschlüsselung und -rechteschutz</span><span class="sxs-lookup"><span data-stu-id="8b69f-135">Remove O365 Message Encryption and rights protection</span></span>
- <span data-ttu-id="8b69f-136">Entfernen</span><span class="sxs-lookup"><span data-stu-id="8b69f-136">Remove</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="8b69f-137">Outlook 2013 und höher unterstützt das Anzeigen von Richtlinientipps für nur einige Bedingungen und Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="8b69f-137">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="8b69f-138">Derzeit unterstützt Outlook 2013 und höher das Anzeigen von Richtlinientipps für Richtlinien, die abgesehen von den unten genannten Bedingungen und entsprechenden Ausnahmen keine Bedingung oder Ausnahme enthalten:</span><span class="sxs-lookup"><span data-stu-id="8b69f-138">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="8b69f-139">Inhalt enthält (funktioniert nur für Typen vertraulicher Informationen.</span><span class="sxs-lookup"><span data-stu-id="8b69f-139">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="8b69f-140">Vertraulichkeitsbezeichnungen werden nicht unterstützt)</span><span class="sxs-lookup"><span data-stu-id="8b69f-140">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="8b69f-141">Inhalt wird freigegeben</span><span class="sxs-lookup"><span data-stu-id="8b69f-141">Content is shared</span></span>

<span data-ttu-id="8b69f-142">Beachten Sie, dass alle Bedingungen für E-Mails funktionieren, die in der Outlook-Client-App verfasst wurden und inhalte übereinstimmen und Schutzmaßnahmen für Inhalte erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8b69f-142">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="8b69f-143">Das Anzeigen von Richtlinientipps für Benutzer wird jedoch für bedingungen, die abgesehen von den oben genannten verwendet werden, noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b69f-143">However, showing policy tips to users is not yet supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="8b69f-144">Outlook 2013 und höher unterstützt das Anzeigen von Richtlinientipps nur für einige Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="8b69f-144">Outlook 2013 and later supports showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="8b69f-145">Die Liste der sofort verwendeten Typen vertraulicher Informationen, die für die Anzeige von DLP-Richtlinientipps in Outlook on Desktop (2013 und höher) erkannt werden, sind die folgenden:</span><span class="sxs-lookup"><span data-stu-id="8b69f-145">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) are the following :</span></span>

- <span data-ttu-id="8b69f-146">ABA Routing Number (US-Bankleitzahl)</span><span class="sxs-lookup"><span data-stu-id="8b69f-146">ABA Routing Number</span></span>
- <span data-ttu-id="8b69f-147">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-147">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="8b69f-148">Australische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-148">Australia Bank Account Number</span></span>
- <span data-ttu-id="8b69f-149">Australische Medical Account-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-149">Australia Medical Account Number</span></span>
- <span data-ttu-id="8b69f-150">Australische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-150">Australia Passport Number</span></span>
- <span data-ttu-id="8b69f-151">Australische Steuernummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-151">Australia Tax File Number</span></span>
- <span data-ttu-id="8b69f-152">Azure DocumentDB-Authentifizierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="8b69f-152">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="8b69f-153">Azure IAAS Database Connection String und Azure SQL Connection String</span><span class="sxs-lookup"><span data-stu-id="8b69f-153">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="8b69f-154">Azure IoT-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b69f-154">Azure IoT Connection String</span></span>  
- <span data-ttu-id="8b69f-155">Azure Publish Setting Password</span><span class="sxs-lookup"><span data-stu-id="8b69f-155">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="8b69f-156">Azure Redis Cache Connection String</span><span class="sxs-lookup"><span data-stu-id="8b69f-156">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="8b69f-157">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="8b69f-157">Azure SAS</span></span>  
- <span data-ttu-id="8b69f-158">Azure Service Bus Connection String</span><span class="sxs-lookup"><span data-stu-id="8b69f-158">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="8b69f-159">Azure Storage Account Key</span><span class="sxs-lookup"><span data-stu-id="8b69f-159">Azure Storage Account Key</span></span>  
- <span data-ttu-id="8b69f-160">Azure Storage Account Key (Generisch)</span><span class="sxs-lookup"><span data-stu-id="8b69f-160">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="8b69f-161">Nationale belgische Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-161">Belgium National Number</span></span>
- <span data-ttu-id="8b69f-162">Brazil CPF Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-162">Brazil CPF Number</span></span>
- <span data-ttu-id="8b69f-163">Brasilien – Juristische Personennummer (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="8b69f-163">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="8b69f-164">	Brasilien – Personalausweis (RG)</span><span class="sxs-lookup"><span data-stu-id="8b69f-164">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="8b69f-165">Kanadische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-165">Canada Bank Account Number</span></span>
- <span data-ttu-id="8b69f-166">Kanadische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-166">Canada Driver's License Number</span></span>
- <span data-ttu-id="8b69f-167">Kanadische Health Service-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-167">Canada Health Service Number</span></span>
- <span data-ttu-id="8b69f-168">Kanadische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-168">Canada Passport Number</span></span>
- <span data-ttu-id="8b69f-169">Kanadische Personal Health Identification-Nummer (PHIN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-169">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="8b69f-170">Kanadische Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-170">Canada Social Insurance Number</span></span>
- <span data-ttu-id="8b69f-171">	Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-171">Chile Identity Card Number</span></span>
- <span data-ttu-id="8b69f-172">	China (PRC) – Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-172">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="8b69f-173">Kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-173">Credit Card Number</span></span>
- <span data-ttu-id="8b69f-174">Kroatische ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-174">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="8b69f-175">Kroatische persönliche ID-Nummer (OIB)</span><span class="sxs-lookup"><span data-stu-id="8b69f-175">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="8b69f-176">Tschechische Persönliche Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-176">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="8b69f-177">Dänische persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-177">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="8b69f-178">Drug Enforcement Agency (DEA)-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-178">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="8b69f-179">EU-Debitkartennummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-179">EU Debit Card Number</span></span>
- <span data-ttu-id="8b69f-180">EU-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-180">EU Driver's License Number</span></span>  
- <span data-ttu-id="8b69f-181">Nationale EU-Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-181">EU National Identification Number</span></span>  
- <span data-ttu-id="8b69f-182">EU-Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-182">EU Passport Number</span></span>  
- <span data-ttu-id="8b69f-183">EU-Sozialversicherungsnummer (SSN) oder Äquivalent-ID</span><span class="sxs-lookup"><span data-stu-id="8b69f-183">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="8b69f-184">EU Tax Identification Number (TIN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-184">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="8b69f-185">Nationale finnische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-185">Finland National ID</span></span>
- <span data-ttu-id="8b69f-186">Finnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-186">Finland Passport Number</span></span>
- <span data-ttu-id="8b69f-187">Französische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-187">France Driver's License Number</span></span>
- <span data-ttu-id="8b69f-188">Französischer Personalausweis (Carte Nationale d'Identité, CNI)</span><span class="sxs-lookup"><span data-stu-id="8b69f-188">France National ID Card (CNI)</span></span>
- <span data-ttu-id="8b69f-189">Französische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-189">France Passport Number</span></span>
- <span data-ttu-id="8b69f-190">Französische Sozialversicherungsnummer (INSEE)</span><span class="sxs-lookup"><span data-stu-id="8b69f-190">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="8b69f-191">Deutsche Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-191">German Driver's License Number</span></span>
- <span data-ttu-id="8b69f-192">Deutsche Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-192">German Passport Number</span></span>
- <span data-ttu-id="8b69f-193">Deutsche Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-193">Germany Identity Card Number</span></span>
- <span data-ttu-id="8b69f-194">Nationale griechische ID-Karte</span><span class="sxs-lookup"><span data-stu-id="8b69f-194">Greece National ID Card</span></span>  
- <span data-ttu-id="8b69f-195">Hongkong (HKID) - Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-195">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="8b69f-196">Indien – Permanente Kontonummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-196">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="8b69f-197">Indien - Eindeutige Identifikationsnummer (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="8b69f-197">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="8b69f-198">Indonesien – Perosonalausweisnummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="8b69f-198">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="8b69f-199">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-199">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="8b69f-200">International Classification of Diseases (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="8b69f-200">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="8b69f-201">International Classification of Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="8b69f-201">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="8b69f-202">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="8b69f-202">IP Address</span></span>
- <span data-ttu-id="8b69f-203">Irische PPS-Nummer (Personal Public Service)</span><span class="sxs-lookup"><span data-stu-id="8b69f-203">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="8b69f-204">Israelische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-204">Israel Bank Account Number</span></span>
- <span data-ttu-id="8b69f-205">Israelische Ausweis-ID</span><span class="sxs-lookup"><span data-stu-id="8b69f-205">Israel National ID</span></span>
- <span data-ttu-id="8b69f-206">Italienische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-206">Italy Driver's License Number</span></span>
- <span data-ttu-id="8b69f-207">Japanische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-207">Japan Bank Account Number</span></span>
- <span data-ttu-id="8b69f-208">Japanische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-208">Japan Driver's License Number</span></span>
- <span data-ttu-id="8b69f-209">Japanische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-209">Japan Passport Number</span></span>
- <span data-ttu-id="8b69f-210">Japanische Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-210">Japan Resident Registration Number</span></span>
- <span data-ttu-id="8b69f-211">Japanische Sozialversicherungsnummer (SIN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-211">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="8b69f-212">Japanische Wohnsitzkartennummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-212">Japanese Residence Card Number</span></span>
- <span data-ttu-id="8b69f-213">Malaysia Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-213">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="8b69f-214">Nummer des niederländischen Citizen's Service (BSN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-214">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="8b69f-215">Neuseeländische Gesundheitsministeriumsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-215">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="8b69f-216">Norwegische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-216">Norway Identity Number</span></span>  
- <span data-ttu-id="8b69f-217">Philippinen – Vereinheitlichte Mehrzweck-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-217">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="8b69f-218">Polnische Identitätskarte</span><span class="sxs-lookup"><span data-stu-id="8b69f-218">Poland Identity Card</span></span>
- <span data-ttu-id="8b69f-219">Nationale polnische ID-Nummer (PESEL)</span><span class="sxs-lookup"><span data-stu-id="8b69f-219">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="8b69f-220">Polnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-220">Poland Passport</span></span>
- <span data-ttu-id="8b69f-221">Portugiesische ID-Kartennummer (Citizen Card)</span><span class="sxs-lookup"><span data-stu-id="8b69f-221">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="8b69f-222">Saudi-Arabische Ausweisnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-222">Saudi Arabia National ID</span></span>
- <span data-ttu-id="8b69f-223">Singapur – National Registration Identity Card-Nummer (NRIC)</span><span class="sxs-lookup"><span data-stu-id="8b69f-223">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="8b69f-224">Südafrika – Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-224">South Africa Identification Number</span></span>  
- <span data-ttu-id="8b69f-225">Südkorea – Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-225">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="8b69f-226">Spanische Sozialversicherungsnummer (SSN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-226">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="8b69f-227">SQL Server Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b69f-227">SQL Server Connection String</span></span>  
- <span data-ttu-id="8b69f-228">Nationale schwedische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-228">Sweden National ID</span></span>
- <span data-ttu-id="8b69f-229">Schwedische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-229">Sweden Passport Number</span></span>
- <span data-ttu-id="8b69f-230">SWIFT-Code</span><span class="sxs-lookup"><span data-stu-id="8b69f-230">SWIFT Code</span></span>
- <span data-ttu-id="8b69f-231">Taiwanesicher Personalausweis</span><span class="sxs-lookup"><span data-stu-id="8b69f-231">Taiwan National ID</span></span>
- <span data-ttu-id="8b69f-232">	Taiwan – Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-232">Taiwan Passport Number</span></span>
- <span data-ttu-id="8b69f-233">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="8b69f-233">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="8b69f-234">Thai Population Identification Code</span><span class="sxs-lookup"><span data-stu-id="8b69f-234">Thai Population Identification Code</span></span>
- <span data-ttu-id="8b69f-235">Nationale Identifikationsnummer der Türkei</span><span class="sxs-lookup"><span data-stu-id="8b69f-235">Turkish National Identification number</span></span>
- <span data-ttu-id="8b69f-p103">Vereinigtes Königreich – Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="8b69f-p104">Vereinigtes Königreich – Wählerverzeichnisnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="8b69f-p105">UK-Gesundheitsdienstnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="8b69f-p106">UK-Sozialversicherungsnummer (National Insurance Number, NINO)</span><span class="sxs-lookup"><span data-stu-id="8b69f-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="8b69f-244">USA/Vereinigtes Königreich</span><span class="sxs-lookup"><span data-stu-id="8b69f-244">U.S. / U.K.</span></span> <span data-ttu-id="8b69f-245">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-245">Passport Number</span></span>
- <span data-ttu-id="8b69f-246">US-Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-246">U.S. Bank Account Number</span></span>
- <span data-ttu-id="8b69f-247">US-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-247">U.S. Driver's License Number</span></span>
- <span data-ttu-id="8b69f-248">US-Steueridentifikationsnummer (ITIN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-248">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="8b69f-249">US-Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-249">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="8b69f-250">Beachten Sie, dass benutzerdefinierte Typen vertraulicher Informationen zusätzlich zu den oben genannten typen für vertrauliche Informationen auch für DLP-Richtlinientipps unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8b69f-250">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="8b69f-251">Verhinderung von Datenverlust auf Endpunkt unterstützt Richtlinientipps nur für einige typen von vertraulichen Informationen</span><span class="sxs-lookup"><span data-stu-id="8b69f-251">Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="8b69f-252">Die Liste der sofort verwendeten Typen vertraulicher Informationen, die in Dokumenten erkannt werden, die sich auf Endpunktgeräten befinden, sind folgende:</span><span class="sxs-lookup"><span data-stu-id="8b69f-252">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="8b69f-253">ABA Routing Number (US-Bankleitzahl)</span><span class="sxs-lookup"><span data-stu-id="8b69f-253">ABA Routing Number</span></span> 
- <span data-ttu-id="8b69f-254">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-254">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="8b69f-255">Australische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-255">Australia Bank Account Number</span></span> 
- <span data-ttu-id="8b69f-256">Australische Medical Account-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-256">Australia Medical Account Number</span></span> 
- <span data-ttu-id="8b69f-257">Australische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-257">Australia Passport Number</span></span> 
- <span data-ttu-id="8b69f-258">Australische Steuernummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-258">Australia Tax File Number</span></span> 
- <span data-ttu-id="8b69f-259">Australische Geschäftsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-259">Australian Business Number</span></span> 
- <span data-ttu-id="8b69f-260">Australische Firmennummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-260">Australian Company Number</span></span> 
- <span data-ttu-id="8b69f-261">Austria Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-261">Austria Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-262">Austria Identity Card</span><span class="sxs-lookup"><span data-stu-id="8b69f-262">Austria Identity Card</span></span> 
- <span data-ttu-id="8b69f-263">Austria Passport Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-263">Austria Passport Number</span></span> 
- <span data-ttu-id="8b69f-264">Österreich Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-264">Austria Social Security Number</span></span> 
- <span data-ttu-id="8b69f-265">Steueridentifikationsnummer für Österreich</span><span class="sxs-lookup"><span data-stu-id="8b69f-265">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="8b69f-266">Austria Value Added Tax (VAT) Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-266">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="8b69f-267">Azure DocumentDB-Authentifizierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="8b69f-267">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="8b69f-268">Azure IAAS Database Connection String und Azure SQL Connection String</span><span class="sxs-lookup"><span data-stu-id="8b69f-268">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="8b69f-269">Azure IoT-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b69f-269">Azure IoT Connection String</span></span> 
- <span data-ttu-id="8b69f-270">Azure Publish Setting Password</span><span class="sxs-lookup"><span data-stu-id="8b69f-270">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="8b69f-271">Azure Redis Cache Connection String</span><span class="sxs-lookup"><span data-stu-id="8b69f-271">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="8b69f-272">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="8b69f-272">Azure SAS</span></span> 
- <span data-ttu-id="8b69f-273">Azure Service Bus Connection String</span><span class="sxs-lookup"><span data-stu-id="8b69f-273">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="8b69f-274">Azure Storage Account Key</span><span class="sxs-lookup"><span data-stu-id="8b69f-274">Azure Storage Account Key</span></span> 
- <span data-ttu-id="8b69f-275">Azure Storage Account Key (Generisch)</span><span class="sxs-lookup"><span data-stu-id="8b69f-275">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="8b69f-276">Belgische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-276">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-277">Nationale belgische Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-277">Belgium National Number</span></span> 
- <span data-ttu-id="8b69f-278">Belgische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-278">Belgium Passport Number</span></span> 
- <span data-ttu-id="8b69f-279">Belgische Umsatzsteuernummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-279">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="8b69f-280">Brazil CPF Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-280">Brazil CPF Number</span></span> 
- <span data-ttu-id="8b69f-281">Brasilien – Juristische Personennummer (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="8b69f-281">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="8b69f-282">	Brasilien – Personalausweis (RG)</span><span class="sxs-lookup"><span data-stu-id="8b69f-282">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="8b69f-283">Kennzeichen des Bulgarien-Führerscheins</span><span class="sxs-lookup"><span data-stu-id="8b69f-283">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-284">Bulgarien Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-284">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="8b69f-285">Uniform Civil Number (Bulgarien)</span><span class="sxs-lookup"><span data-stu-id="8b69f-285">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="8b69f-286">Kanadische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-286">Canada Bank Account Number</span></span> 
- <span data-ttu-id="8b69f-287">Kanadische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-287">Canada Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-288">Kanadische Health Service-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-288">Canada Health Service Number</span></span> 
- <span data-ttu-id="8b69f-289">Kanadische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-289">Canada Passport Number</span></span> 
- <span data-ttu-id="8b69f-290">Kanadische Personal Health Identification-Nummer (PHIN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-290">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="8b69f-291">Kanadische Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-291">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="8b69f-292">	Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-292">Chile Identity Card Number</span></span> 
- <span data-ttu-id="8b69f-293">	China (PRC) – Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-293">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="8b69f-294">Kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-294">Credit Card Number</span></span> 
- <span data-ttu-id="8b69f-295">Kroatische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-295">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-296">Kroatische ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-296">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="8b69f-297">Kroatische Nationale ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-297">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="8b69f-298">Kroatische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-298">Croatia Passport Number</span></span> 
- <span data-ttu-id="8b69f-299">Kroatische persönliche ID-Nummer (OIB)</span><span class="sxs-lookup"><span data-stu-id="8b69f-299">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="8b69f-300">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span><span class="sxs-lookup"><span data-stu-id="8b69f-300">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="8b69f-301">CSCAN-GENERAL0140 Allgemeiner symmetrischer Schlüssel</span><span class="sxs-lookup"><span data-stu-id="8b69f-301">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="8b69f-302">Zyprische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-302">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-303">Identitätskarte für Zypern</span><span class="sxs-lookup"><span data-stu-id="8b69f-303">Cyprus Identity Card</span></span> 
- <span data-ttu-id="8b69f-304">Reisepassnummer für Zypern</span><span class="sxs-lookup"><span data-stu-id="8b69f-304">Cyprus Passport Number</span></span> 
- <span data-ttu-id="8b69f-305">Steueridentifikationsnummer für Zypern</span><span class="sxs-lookup"><span data-stu-id="8b69f-305">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="8b69f-306">Tschechische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-306">Czech Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-307">Tschechische Persönliche Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-307">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="8b69f-308">Tschechische Republik Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-308">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="8b69f-309">Dänische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-309">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-310">Dänische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-310">Denmark Passport Number</span></span> 
- <span data-ttu-id="8b69f-311">Dänische persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-311">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="8b69f-312">Drug Enforcement Agency (DEA)-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-312">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="8b69f-313">Estonia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-313">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-314">Estonia Passport Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-314">Estonia Passport Number</span></span> 
- <span data-ttu-id="8b69f-315">Estonia Personal Identification Code</span><span class="sxs-lookup"><span data-stu-id="8b69f-315">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="8b69f-316">EU-Debitkartennummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-316">EU Debit Card Number</span></span> 
- <span data-ttu-id="8b69f-317">EU-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-317">EU Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-318">Nationale EU-Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-318">EU National Identification Number</span></span> 
- <span data-ttu-id="8b69f-319">EU-Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-319">EU Passport Number</span></span> 
- <span data-ttu-id="8b69f-320">EU-Sozialversicherungsnummer (SSN) oder Äquivalent-ID</span><span class="sxs-lookup"><span data-stu-id="8b69f-320">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="8b69f-321">EU Tax Identification Number (TIN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-321">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="8b69f-322">Finland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-322">Finland Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-323">Finnland Europäische Krankenversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-323">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="8b69f-324">Nationale finnische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-324">Finland National ID</span></span> 
- <span data-ttu-id="8b69f-325">Finnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-325">Finland Passport Number</span></span> 
- <span data-ttu-id="8b69f-326">Französische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-326">France Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-327">Französische Krankenversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-327">France Health Insurance Number</span></span> 
- <span data-ttu-id="8b69f-328">Französischer Personalausweis (Carte Nationale d'Identité, CNI)</span><span class="sxs-lookup"><span data-stu-id="8b69f-328">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="8b69f-329">Französische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-329">France Passport Number</span></span> 
- <span data-ttu-id="8b69f-330">Französische Sozialversicherungsnummer (INSEE)</span><span class="sxs-lookup"><span data-stu-id="8b69f-330">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="8b69f-331">Französische Steueridentifikationsnummer (numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="8b69f-331">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="8b69f-332">Französische Umsatzsteuernummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-332">France Value Added Tax Number</span></span> 
- <span data-ttu-id="8b69f-333">Deutsche Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-333">German Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-334">Deutsche Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-334">German Passport Number</span></span> 
- <span data-ttu-id="8b69f-335">Deutsche Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-335">Germany Identity Card Number</span></span> 
- <span data-ttu-id="8b69f-336">Deutsche Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-336">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="8b69f-337">Deutsche Umsatzsteuernummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-337">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="8b69f-338">Führerscheinnummer für Griechenland</span><span class="sxs-lookup"><span data-stu-id="8b69f-338">Greece Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-339">Nationale griechische ID-Karte</span><span class="sxs-lookup"><span data-stu-id="8b69f-339">Greece National ID Card</span></span> 
- <span data-ttu-id="8b69f-340">Griechenland Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-340">Greece Passport Number</span></span> 
- <span data-ttu-id="8b69f-341">Griechenland Sozialversicherungsnummer (AMKA)</span><span class="sxs-lookup"><span data-stu-id="8b69f-341">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="8b69f-342">Griechische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-342">Greek Tax identification Number</span></span> 
- <span data-ttu-id="8b69f-343">Hongkong (HKID) - Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-343">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="8b69f-344">Ungarische Sozialversicherungsnummer (TAJ)</span><span class="sxs-lookup"><span data-stu-id="8b69f-344">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="8b69f-345">Mehrwertsteuernummer für Ungarn</span><span class="sxs-lookup"><span data-stu-id="8b69f-345">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="8b69f-346">Kennzeichen des Ungarn-Führerscheins</span><span class="sxs-lookup"><span data-stu-id="8b69f-346">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-347">Ungarn Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-347">Hungary Passport Number</span></span> 
- <span data-ttu-id="8b69f-348">Ungarn Persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-348">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="8b69f-349">Ungarn Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-349">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="8b69f-350">Indien – Permanente Kontonummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-350">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="8b69f-351">Indien - Eindeutige Identifikationsnummer (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="8b69f-351">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="8b69f-352">Indonesien – Perosonalausweisnummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="8b69f-352">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="8b69f-353">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-353">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="8b69f-354">International Classification of Diseases (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="8b69f-354">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="8b69f-355">International Classification of Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="8b69f-355">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="8b69f-356">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="8b69f-356">IP Address</span></span> 
- <span data-ttu-id="8b69f-357">Ireland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-357">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-358">Irland Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-358">Ireland Passport Number</span></span> 
- <span data-ttu-id="8b69f-359">Irische PPS-Nummer (Personal Public Service)</span><span class="sxs-lookup"><span data-stu-id="8b69f-359">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="8b69f-360">Israelische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-360">Israel Bank Account Number</span></span> 
- <span data-ttu-id="8b69f-361">Israelische Ausweis-ID</span><span class="sxs-lookup"><span data-stu-id="8b69f-361">Israel National ID</span></span> 
- <span data-ttu-id="8b69f-362">Italienische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-362">Italy Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-363">Steuercode für Italien</span><span class="sxs-lookup"><span data-stu-id="8b69f-363">Italy Fiscal Code</span></span> 
- <span data-ttu-id="8b69f-364">Italienische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-364">Italy Passport Number</span></span> 
- <span data-ttu-id="8b69f-365">Italienische Mehrwertsteuernummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-365">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="8b69f-366">Japanische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-366">Japan Bank Account Number</span></span> 
- <span data-ttu-id="8b69f-367">Japanische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-367">Japan Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-368">Japanische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-368">Japan Passport Number</span></span> 
- <span data-ttu-id="8b69f-369">Japanische Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-369">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="8b69f-370">Japanische Sozialversicherungsnummer (SIN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-370">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="8b69f-371">Japanische My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="8b69f-371">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="8b69f-372">Japanisch My Number Personal</span><span class="sxs-lookup"><span data-stu-id="8b69f-372">Japanese My Number Personal</span></span> 
- <span data-ttu-id="8b69f-373">Japanische Wohnsitzkartennummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-373">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="8b69f-374">Latvia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-374">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-375">Latvia Passport Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-375">Latvia Passport Number</span></span> 
- <span data-ttu-id="8b69f-376">Persönlichen Code für Lettland</span><span class="sxs-lookup"><span data-stu-id="8b69f-376">Latvia Personal Code</span></span> 
- <span data-ttu-id="8b69f-377">Lizenznummer des Litauen-Führerscheins</span><span class="sxs-lookup"><span data-stu-id="8b69f-377">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-378">Reisepassnummer für Litauen</span><span class="sxs-lookup"><span data-stu-id="8b69f-378">Lithuania Passport Number</span></span> 
- <span data-ttu-id="8b69f-379">Persönlichen Code für Litauen</span><span class="sxs-lookup"><span data-stu-id="8b69f-379">Lithuania Personal Code</span></span> 
- <span data-ttu-id="8b69f-380">LuxemburgEr Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-380">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-381">Nationale Identifikationsnummer (natürliche Personen)</span><span class="sxs-lookup"><span data-stu-id="8b69f-381">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="8b69f-382">Nationale Identifikationsnummer (nicht natürliche Personen)</span><span class="sxs-lookup"><span data-stu-id="8b69f-382">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="8b69f-383">Luxemburg Passport Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-383">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="8b69f-384">Malaysia Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-384">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="8b69f-385">Malta Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-385">Malta Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-386">Malta Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-386">Malta Identity Card Number</span></span> 
- <span data-ttu-id="8b69f-387">Malta Passport Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-387">Malta Passport Number</span></span> 
- <span data-ttu-id="8b69f-388">Malta Steuer-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-388">Malta Tax ID Number</span></span> 
- <span data-ttu-id="8b69f-389">Nummer des niederländischen Citizen's Service (BSN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-389">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="8b69f-390">Niederländische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-390">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-391">Niederländische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-391">Netherlands Passport Number</span></span> 
- <span data-ttu-id="8b69f-392">Niederländische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-392">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="8b69f-393">Niederländische Umsatzsteuernummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-393">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="8b69f-394">Bankkontonummer für Neuseeland</span><span class="sxs-lookup"><span data-stu-id="8b69f-394">New Zealand bank account number</span></span> 
- <span data-ttu-id="8b69f-395">New Zealand Driver License Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-395">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="8b69f-396">New Zealand Inland Revenue Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-396">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="8b69f-397">Neuseeländische Gesundheitsministeriumsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-397">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="8b69f-398">New Zealand Social Welfare Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-398">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="8b69f-399">Norwegische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-399">Norway Identity Number</span></span> 
- <span data-ttu-id="8b69f-400">Philippinen – Vereinheitlichte Mehrzweck-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-400">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="8b69f-401">Polnische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-401">Poland Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-402">Polnische Identitätskarte</span><span class="sxs-lookup"><span data-stu-id="8b69f-402">Poland Identity Card</span></span> 
- <span data-ttu-id="8b69f-403">Nationale polnische ID-Nummer (PESEL)</span><span class="sxs-lookup"><span data-stu-id="8b69f-403">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="8b69f-404">Polnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-404">Poland Passport</span></span> 
- <span data-ttu-id="8b69f-405">Polnische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-405">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="8b69f-406">Polnische REGON-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-406">Polish REGON Number</span></span> 
- <span data-ttu-id="8b69f-407">Portugiesische ID-Kartennummer (Citizen Card)</span><span class="sxs-lookup"><span data-stu-id="8b69f-407">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="8b69f-408">Portugal Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-408">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-409">Portugal Passport Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-409">Portugal Passport Number</span></span> 
- <span data-ttu-id="8b69f-410">Steueridentifikationsnummer für Portugal</span><span class="sxs-lookup"><span data-stu-id="8b69f-410">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="8b69f-411">Romania Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-411">Romania Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-412">Rumänien Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-412">Romania Passport Number</span></span> 
- <span data-ttu-id="8b69f-413">Rumänien – Persönlicher numerischer Code (CNP)</span><span class="sxs-lookup"><span data-stu-id="8b69f-413">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="8b69f-414">Russische Reisepassnummer (Inland)</span><span class="sxs-lookup"><span data-stu-id="8b69f-414">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="8b69f-415">Russische Reisepassnummer (International)</span><span class="sxs-lookup"><span data-stu-id="8b69f-415">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="8b69f-416">Saudi-Arabische Ausweisnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-416">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="8b69f-417">Singapur – National Registration Identity Card-Nummer (NRIC)</span><span class="sxs-lookup"><span data-stu-id="8b69f-417">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="8b69f-418">Slovakia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-418">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-419">Slowakei Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-419">Slovakia Passport Number</span></span> 
- <span data-ttu-id="8b69f-420">Persönliche Nummer der Slowakei</span><span class="sxs-lookup"><span data-stu-id="8b69f-420">Slovakia Personal Number</span></span> 
- <span data-ttu-id="8b69f-421">Slovenia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-421">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-422">Slowenien Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-422">Slovenia Passport Number</span></span> 
- <span data-ttu-id="8b69f-423">Slowenien Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-423">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="8b69f-424">Slowenien Eindeutige Master Citizen Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-424">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="8b69f-425">Südafrika – Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-425">South Africa Identification Number</span></span> 
- <span data-ttu-id="8b69f-426">Südkorea – Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-426">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="8b69f-427">Spanien DNI</span><span class="sxs-lookup"><span data-stu-id="8b69f-427">Spain DNI</span></span> 
- <span data-ttu-id="8b69f-428">Spain Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-428">Spain Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-429">Spanische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-429">Spain Passport Number</span></span> 
- <span data-ttu-id="8b69f-430">Spanische Sozialversicherungsnummer (SSN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-430">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="8b69f-431">Spanien Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-431">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="8b69f-432">SQL Server Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b69f-432">SQL Server Connection String</span></span> 
- <span data-ttu-id="8b69f-433">Schwedische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-433">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-434">Nationale schwedische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-434">Sweden National ID</span></span> 
- <span data-ttu-id="8b69f-435">Schwedische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-435">Sweden Passport Number</span></span> 
- <span data-ttu-id="8b69f-436">Steueridentifikationsnummer für Schweden</span><span class="sxs-lookup"><span data-stu-id="8b69f-436">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="8b69f-437">SWIFT-Code</span><span class="sxs-lookup"><span data-stu-id="8b69f-437">SWIFT Code</span></span> 
- <span data-ttu-id="8b69f-438">Swiss Social Security Number AHV</span><span class="sxs-lookup"><span data-stu-id="8b69f-438">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="8b69f-439">Taiwanesicher Personalausweis</span><span class="sxs-lookup"><span data-stu-id="8b69f-439">Taiwan National ID</span></span> 
- <span data-ttu-id="8b69f-440">	Taiwan – Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-440">Taiwan Passport Number</span></span> 
- <span data-ttu-id="8b69f-441">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="8b69f-441">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="8b69f-442">Thai Population Identification Code</span><span class="sxs-lookup"><span data-stu-id="8b69f-442">Thai Population Identification Code</span></span> 
- <span data-ttu-id="8b69f-443">Nationale Identifikationsnummer der Türkei</span><span class="sxs-lookup"><span data-stu-id="8b69f-443">Turkish National Identification number</span></span> 
- <span data-ttu-id="8b69f-p108">Vereinigtes Königreich – Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-p109">Vereinigtes Königreich – Wählerverzeichnisnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="8b69f-p110">UK-Gesundheitsdienstnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="8b69f-p111">UK-Sozialversicherungsnummer (National Insurance Number, NINO)</span><span class="sxs-lookup"><span data-stu-id="8b69f-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="8b69f-452">Vereinigtes Königreich</span><span class="sxs-lookup"><span data-stu-id="8b69f-452">U.K.</span></span> <span data-ttu-id="8b69f-453">Eindeutige Steuernummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-453">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="8b69f-454">USA/Vereinigtes Königreich</span><span class="sxs-lookup"><span data-stu-id="8b69f-454">U.S. / U.K.</span></span> <span data-ttu-id="8b69f-455">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8b69f-455">Passport Number</span></span> 
- <span data-ttu-id="8b69f-456">US-Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-456">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="8b69f-457">US-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-457">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="8b69f-458">US-Steueridentifikationsnummer (ITIN)</span><span class="sxs-lookup"><span data-stu-id="8b69f-458">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="8b69f-459">US-Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="8b69f-459">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="8b69f-460">Ukraine Passport Number (Inland)</span><span class="sxs-lookup"><span data-stu-id="8b69f-460">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="8b69f-461">Ukraine Passport Number (International)</span><span class="sxs-lookup"><span data-stu-id="8b69f-461">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="8b69f-462">Bitte beachten Sie, dass zusätzlich zu den oben genannten sofort verwendeten Typen vertraulicher Informationen auch benutzerdefinierte Typen vertraulicher Informationen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="8b69f-462">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="8b69f-463">Support matrix for DLP policy tips across Microsoft apps</span><span class="sxs-lookup"><span data-stu-id="8b69f-463">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="8b69f-464">**App und Plattform**</span><span class="sxs-lookup"><span data-stu-id="8b69f-464">**App and platform**</span></span>|<span data-ttu-id="8b69f-465">**Unterstützung von DLP-Richtlinientipps**</span><span class="sxs-lookup"><span data-stu-id="8b69f-465">**DLP policy tip support**</span></span>|<span data-ttu-id="8b69f-466">**Unterstützte Typen vertraulicher Informationen**</span><span class="sxs-lookup"><span data-stu-id="8b69f-466">**Sensitive information types supported**</span></span>|<span data-ttu-id="8b69f-467">**Unterstützte Prädikate und Aktionen**</span><span class="sxs-lookup"><span data-stu-id="8b69f-467">**Predicates and actions supported**</span></span>|<span data-ttu-id="8b69f-468">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="8b69f-468">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="8b69f-469">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="8b69f-469">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8b69f-470">Alle</span><span class="sxs-lookup"><span data-stu-id="8b69f-470">All</span></span>|<span data-ttu-id="8b69f-471">Subset</span><span class="sxs-lookup"><span data-stu-id="8b69f-471">Subset</span></span>|<span data-ttu-id="8b69f-472">Siehe [Hinweise zu Richtlinientipps zur](#data-loss-prevention-policy-tips-reference) Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="8b69f-472">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="8b69f-473">**Outlook Win32 (Outlook 2013 und darüber hinaus)**</span><span class="sxs-lookup"><span data-stu-id="8b69f-473">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8b69f-474">Subset</span><span class="sxs-lookup"><span data-stu-id="8b69f-474">Subset</span></span>|<span data-ttu-id="8b69f-475">Subset</span><span class="sxs-lookup"><span data-stu-id="8b69f-475">Subset</span></span>|<span data-ttu-id="8b69f-476">Unter [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) und höher werden Richtlinientipps für nur einige Bedingungen und Ausnahmen sowie Outlook 2013 und höher unterstützt, in denen Richtlinientipps nur für einige typen vertraulicher Informationen angezeigt werden. Weitere Informationen zur Unterstützung vertraulicher Informationstypen sowie von DLP-Bedingungen und -Aktionen, die für die Anzeige von DLP-Richtlinientipps in Outlook Win32 unterstützt werden, finden Sie unter Outlook [2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) und höher.</span><span class="sxs-lookup"><span data-stu-id="8b69f-476">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later supports showing policy tips for only some sensitive information types](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="8b69f-477">**Outlook Mobile (iOS, Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="8b69f-477">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8b69f-478">Keine</span><span class="sxs-lookup"><span data-stu-id="8b69f-478">None</span></span>|<span data-ttu-id="8b69f-479">Keine</span><span class="sxs-lookup"><span data-stu-id="8b69f-479">None</span></span>|<span data-ttu-id="8b69f-480">DLP-Richtlinientipps werden auf Outlook mobilen Geräten nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="8b69f-480">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="8b69f-481">**Sharepoint Online/One Drive for Business Web Client**</span><span class="sxs-lookup"><span data-stu-id="8b69f-481">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8b69f-482">Alle</span><span class="sxs-lookup"><span data-stu-id="8b69f-482">All</span></span>|<span data-ttu-id="8b69f-483">Alle SPO/ODB-Prädikate und -Aktionen in DLP</span><span class="sxs-lookup"><span data-stu-id="8b69f-483">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="8b69f-484">**Sharepoint Win32/ One Drive for Business Win32-Client**</span><span class="sxs-lookup"><span data-stu-id="8b69f-484">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8b69f-485">Keine</span><span class="sxs-lookup"><span data-stu-id="8b69f-485">None</span></span>|<span data-ttu-id="8b69f-486">Keine</span><span class="sxs-lookup"><span data-stu-id="8b69f-486">None</span></span>|<span data-ttu-id="8b69f-487">#A0 werden in Sharepoint- oder OneDrive-Desktopclient-Apps nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="8b69f-487">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="8b69f-488">**Word, Excel, Powerpoint Web Client**</span><span class="sxs-lookup"><span data-stu-id="8b69f-488">**Word, Excel, Powerpoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8b69f-489">Alle</span><span class="sxs-lookup"><span data-stu-id="8b69f-489">All</span></span>|<span data-ttu-id="8b69f-490">Alle SPO/ODB-Prädikate und -Aktionen in DLP</span><span class="sxs-lookup"><span data-stu-id="8b69f-490">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="8b69f-491">Der Tipp für die DLP-Richtlinie wird unterstützt, wenn das Dokument in spo- oder ODB-Web-App gehostet wird und die DLP-Richtlinie bereits gestempelt ist.</span><span class="sxs-lookup"><span data-stu-id="8b69f-491">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="8b69f-492">**Word, Excel, Powerpoint Mobile Client**</span><span class="sxs-lookup"><span data-stu-id="8b69f-492">**Word, Excel, Powerpoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8b69f-493">Keine</span><span class="sxs-lookup"><span data-stu-id="8b69f-493">None</span></span>|<span data-ttu-id="8b69f-494">Keine</span><span class="sxs-lookup"><span data-stu-id="8b69f-494">None</span></span>|<span data-ttu-id="8b69f-495">DLP-Richtlinientipps werden in mobilen Apps für Office nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b69f-495">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="8b69f-496">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="8b69f-496">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8b69f-497">Alle</span><span class="sxs-lookup"><span data-stu-id="8b69f-497">All</span></span>|<span data-ttu-id="8b69f-498">Alle Teams-Prädikate in der DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8b69f-498">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="8b69f-499">Richtlinientipps werden angezeigt, wenn eine Nachricht mit "Diese Nachricht wurde gekennzeichnet" gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="8b69f-499">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="8b69f-500">Was kann ich tun?"</span><span class="sxs-lookup"><span data-stu-id="8b69f-500">What can I do?”</span></span> <span data-ttu-id="8b69f-501">Wenn der Benutzer auf den Link klickt, kann er die erkannten Typen vertraulicher Informationen überprüfen und ein Problem außer Kraft setzen oder melden, wenn dies vom Administrator zulässig ist. Beachten Sie, dass keine Richtlinientipps für Dateien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8b69f-501">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="8b69f-502">Wenn der Empfänger versucht, auf das Dokument zu zugreifen, erhält er möglicherweise zugriff verweigert, wenn er nicht zugelassen ist.</span><span class="sxs-lookup"><span data-stu-id="8b69f-502">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="8b69f-503">**Win32-Endpunktgeräte**</span><span class="sxs-lookup"><span data-stu-id="8b69f-503">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8b69f-504">Subset</span><span class="sxs-lookup"><span data-stu-id="8b69f-504">Subset</span></span>|<span data-ttu-id="8b69f-505">Alle Endpunkt-DLP-Prädikate und -Aktionen in der DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8b69f-505">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="8b69f-506">Weitere [Informationen finden Sie unter Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types.](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="8b69f-506">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="8b69f-507">**Mac-Geräte**</span><span class="sxs-lookup"><span data-stu-id="8b69f-507">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8b69f-508">Keine</span><span class="sxs-lookup"><span data-stu-id="8b69f-508">None</span></span>|<span data-ttu-id="8b69f-509">Keine</span><span class="sxs-lookup"><span data-stu-id="8b69f-509">None</span></span>|<span data-ttu-id="8b69f-510">Verhinderung von Datenverlust ist heute auf Mac-Geräten nicht durchsetzbar</span><span class="sxs-lookup"><span data-stu-id="8b69f-510">Data loss prevention are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="8b69f-511">**Cloud-Apps von Drittanbietern**</span><span class="sxs-lookup"><span data-stu-id="8b69f-511">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8b69f-512">Keine</span><span class="sxs-lookup"><span data-stu-id="8b69f-512">None</span></span>|<span data-ttu-id="8b69f-513">Keine</span><span class="sxs-lookup"><span data-stu-id="8b69f-513">None</span></span>|<span data-ttu-id="8b69f-514">Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="8b69f-514">Data Loss Prevention</span></span>|
|<span data-ttu-id="8b69f-515">**On-Prem**</span><span class="sxs-lookup"><span data-stu-id="8b69f-515">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8b69f-516">Keine</span><span class="sxs-lookup"><span data-stu-id="8b69f-516">None</span></span>|<span data-ttu-id="8b69f-517">Keine</span><span class="sxs-lookup"><span data-stu-id="8b69f-517">None</span></span>||
|<span data-ttu-id="8b69f-518">**Word, Excel, Powerpoint Win32 Client**</span><span class="sxs-lookup"><span data-stu-id="8b69f-518">**Word, Excel, Powerpoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8b69f-519">Subset</span><span class="sxs-lookup"><span data-stu-id="8b69f-519">Subset</span></span>|<span data-ttu-id="8b69f-520">Subset</span><span class="sxs-lookup"><span data-stu-id="8b69f-520">Subset</span></span>|<span data-ttu-id="8b69f-521">Richtlinientipps für WXP-Client-Apps funktionieren für Dokumente, die auf Sharepoint Online- oder One Drive for Business-Websites gespeichert sind, für alle DLP-Richtlinien, die genau die folgende oder eine Teilmenge von Bedingungen oder Aktionen in der DLP-Richtlinie enthalten:</span><span class="sxs-lookup"><span data-stu-id="8b69f-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="8b69f-522">Inhalt enthält Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="8b69f-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="8b69f-523">Zugriffsbereich (Inhalt wird intern/extern freigegeben)</span><span class="sxs-lookup"><span data-stu-id="8b69f-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="8b69f-524">Benutzer benachrichtigen (Richtlinientipps/Benutzerbenachrichtigungen)</span><span class="sxs-lookup"><span data-stu-id="8b69f-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="8b69f-525">Blockieren von allen</span><span class="sxs-lookup"><span data-stu-id="8b69f-525">Block everyone</span></span></li><li><span data-ttu-id="8b69f-526">Schadensberichte</span><span class="sxs-lookup"><span data-stu-id="8b69f-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="8b69f-527">Wenn eine andere Bedingung oder Aktion vorhanden ist, wird der DLP-Richtlinientipp für diese Richtlinie nicht in den Desktop-Apps von Word, Excel oder PowerPoint angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8b69f-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span>|
||||||