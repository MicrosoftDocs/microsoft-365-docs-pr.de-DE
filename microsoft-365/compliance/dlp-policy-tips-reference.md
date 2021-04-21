---
title: 'Referenz: Richtlinientipps zur Verhinderung von Datenverlust (Data Loss Prevention, DLP)'
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
ms.openlocfilehash: 36e4d4f96146b51e0b31731c9e93222eed767045
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903802"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="7b92e-103">Referenz: Richtlinientipps zur Verhinderung von Datenverlust (Data Loss Prevention, DLP)</span><span class="sxs-lookup"><span data-stu-id="7b92e-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="7b92e-104">DLP-Richtlinientipps in Outlook Web Access werden für alle Bedingungen, Ausnahmen und Aktionen unterstützt, die für die Exchange-Arbeitsauslastung in einer DLP-Richtlinie gelten, mit Ausnahme der folgenden:</span><span class="sxs-lookup"><span data-stu-id="7b92e-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="7b92e-105">**Bedingungen:**</span><span class="sxs-lookup"><span data-stu-id="7b92e-105">**Conditions:**</span></span>

- <span data-ttu-id="7b92e-106">Sender Is</span><span class="sxs-lookup"><span data-stu-id="7b92e-106">Sender Is</span></span>
- <span data-ttu-id="7b92e-107">Absenderdomäne ist</span><span class="sxs-lookup"><span data-stu-id="7b92e-107">Sender Domain Is</span></span>
- <span data-ttu-id="7b92e-108">Recipient ist Mitglied von</span><span class="sxs-lookup"><span data-stu-id="7b92e-108">Recipient is a member of</span></span>
- <span data-ttu-id="7b92e-109">Kopfzeile enthält Wörter oder Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7b92e-109">Header contains words or phrases</span></span>
- <span data-ttu-id="7b92e-110">Kopfzeile entspricht Mustern</span><span class="sxs-lookup"><span data-stu-id="7b92e-110">Header matches patterns</span></span>
- <span data-ttu-id="7b92e-111">Dokumentgröße gleich oder größer als</span><span class="sxs-lookup"><span data-stu-id="7b92e-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="7b92e-112">Nachrichtentyp ist</span><span class="sxs-lookup"><span data-stu-id="7b92e-112">Message type is</span></span>
- <span data-ttu-id="7b92e-113">Die Wichtigkeit der Nachricht ist</span><span class="sxs-lookup"><span data-stu-id="7b92e-113">Message importance is</span></span>
- <span data-ttu-id="7b92e-114">Inhaltszeichensatz enthält Wörter</span><span class="sxs-lookup"><span data-stu-id="7b92e-114">Content character set contains words</span></span>
- <span data-ttu-id="7b92e-115">Betreff oder Textkörper enthält Wörter oder Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7b92e-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="7b92e-116">Betreff oder Textkörper entspricht Mustern</span><span class="sxs-lookup"><span data-stu-id="7b92e-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="7b92e-117">Inhaltszeichensatz enthält Wörter</span><span class="sxs-lookup"><span data-stu-id="7b92e-117">Content character set contains words</span></span>
- <span data-ttu-id="7b92e-118">Inhalt wird von empfangen</span><span class="sxs-lookup"><span data-stu-id="7b92e-118">Content is received from</span></span>
- <span data-ttu-id="7b92e-119">Hat absender den Richtlinientipp außer Kraft gesetzt</span><span class="sxs-lookup"><span data-stu-id="7b92e-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="7b92e-120">Nachrichtengröße gleich oder größer als</span><span class="sxs-lookup"><span data-stu-id="7b92e-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="7b92e-121">Sender AD-Attribut enthält Wörter oder Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7b92e-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="7b92e-122">Sender AD-Attribut entspricht Mustern</span><span class="sxs-lookup"><span data-stu-id="7b92e-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="7b92e-123">Dokumentinhalt enthält Wörter oder Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7b92e-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="7b92e-124">Dokumentinhalt entspricht Mustern</span><span class="sxs-lookup"><span data-stu-id="7b92e-124">Document content matches patterns</span></span>

<span data-ttu-id="7b92e-125">**Aktionen:**</span><span class="sxs-lookup"><span data-stu-id="7b92e-125">**Actions:**</span></span>

- <span data-ttu-id="7b92e-126">Weiterleiten der Nachricht zur Genehmigung an den Vorgesetzten des Absenders</span><span class="sxs-lookup"><span data-stu-id="7b92e-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="7b92e-127">Weiterleiten der Nachricht zur Genehmigung an bestimmte genehmigende Benutzer</span><span class="sxs-lookup"><span data-stu-id="7b92e-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="7b92e-128">Umleiten der Nachricht an bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="7b92e-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="7b92e-129">Hinzufügen von Empfängern zum Feld An</span><span class="sxs-lookup"><span data-stu-id="7b92e-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="7b92e-130">Hinzufügen von Empfängern zum Cc-Feld</span><span class="sxs-lookup"><span data-stu-id="7b92e-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="7b92e-131">Hinzufügen von Empfängern zum Bcc-Feld</span><span class="sxs-lookup"><span data-stu-id="7b92e-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="7b92e-132">Hinzufügen des Vorgesetzten des Absenders als Empfänger</span><span class="sxs-lookup"><span data-stu-id="7b92e-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="7b92e-133">Hinzufügen eines HTML-Haftungsausschlusses</span><span class="sxs-lookup"><span data-stu-id="7b92e-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="7b92e-134">Vorausgeöffneter E-Mail-Betreff</span><span class="sxs-lookup"><span data-stu-id="7b92e-134">Prepend email subject</span></span>
- <span data-ttu-id="7b92e-135">Entfernen von O365-Nachrichtenverschlüsselung und -rechteschutz</span><span class="sxs-lookup"><span data-stu-id="7b92e-135">Remove O365 Message Encryption and rights protection</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="7b92e-136">Outlook 2013 und höher unterstützt das Anzeigen von Richtlinientipps für nur einige Bedingungen und Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="7b92e-136">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="7b92e-137">Derzeit unterstützt Outlook 2013 und höher das Anzeigen von Richtlinientipps für Richtlinien, die abgesehen von den unten genannten Bedingungen und entsprechenden Ausnahmen keine Bedingung oder Ausnahme enthalten:</span><span class="sxs-lookup"><span data-stu-id="7b92e-137">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="7b92e-138">Inhalt enthält (funktioniert nur für Typen vertraulicher Informationen.</span><span class="sxs-lookup"><span data-stu-id="7b92e-138">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="7b92e-139">Vertraulichkeitsbezeichnungen werden nicht unterstützt)</span><span class="sxs-lookup"><span data-stu-id="7b92e-139">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="7b92e-140">Inhalt wird freigegeben</span><span class="sxs-lookup"><span data-stu-id="7b92e-140">Content is shared</span></span>

<span data-ttu-id="7b92e-141">Beachten Sie, dass alle Bedingungen für E-Mails funktionieren, die in der Outlook-Client-App verfasst wurden und inhalte übereinstimmen und Schutzmaßnahmen für Inhalte erzwingen.</span><span class="sxs-lookup"><span data-stu-id="7b92e-141">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="7b92e-142">Das Anzeigen von Richtlinientipps für Benutzer wird jedoch für bedingungen, die abgesehen von den oben genannten bedingungen verwendet werden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7b92e-142">However, showing policy tips to users is not supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="7b92e-143">Unterstützung für Outlook 2013 und höher und Office-Apps auf Desktop mit Richtlinientipps für nur einige typen von vertraulichen Informationen</span><span class="sxs-lookup"><span data-stu-id="7b92e-143">Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="7b92e-144">Die Liste der sofort verwendeten typen vertraulicher Informationen, die für die Anzeige von DLP-Richtlinientipps in Outlook on Desktop (2013 und höher) und Office-Apps (Word, Excel, PowerPoint) auf Desktop erkannt werden, sind die folgenden:</span><span class="sxs-lookup"><span data-stu-id="7b92e-144">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) and Office apps (Word, Excel, PowerPoint) on Desktop are the following :</span></span>

- <span data-ttu-id="7b92e-145">ABA Routing Number (US-Bankleitzahl)</span><span class="sxs-lookup"><span data-stu-id="7b92e-145">ABA Routing Number</span></span>
- <span data-ttu-id="7b92e-146">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-146">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="7b92e-147">Australische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-147">Australia Bank Account Number</span></span>
- <span data-ttu-id="7b92e-148">Australische Medical Account-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-148">Australia Medical Account Number</span></span>
- <span data-ttu-id="7b92e-149">Australische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-149">Australia Passport Number</span></span>
- <span data-ttu-id="7b92e-150">Australische Steuernummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-150">Australia Tax File Number</span></span>
- <span data-ttu-id="7b92e-151">Azure DocumentDB-Authentifizierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="7b92e-151">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="7b92e-152">Azure IAAS Database Connection String und Azure SQL Connection String</span><span class="sxs-lookup"><span data-stu-id="7b92e-152">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="7b92e-153">Azure IoT-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7b92e-153">Azure IoT Connection String</span></span>  
- <span data-ttu-id="7b92e-154">Azure Publish Setting Password</span><span class="sxs-lookup"><span data-stu-id="7b92e-154">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="7b92e-155">Azure Redis Cache Connection String</span><span class="sxs-lookup"><span data-stu-id="7b92e-155">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="7b92e-156">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="7b92e-156">Azure SAS</span></span>  
- <span data-ttu-id="7b92e-157">Azure Service Bus Connection String</span><span class="sxs-lookup"><span data-stu-id="7b92e-157">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="7b92e-158">Azure Storage Account Key</span><span class="sxs-lookup"><span data-stu-id="7b92e-158">Azure Storage Account Key</span></span>  
- <span data-ttu-id="7b92e-159">Azure Storage Account Key (Generisch)</span><span class="sxs-lookup"><span data-stu-id="7b92e-159">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="7b92e-160">Nationale belgische Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-160">Belgium National Number</span></span>
- <span data-ttu-id="7b92e-161">Brazil CPF Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-161">Brazil CPF Number</span></span>
- <span data-ttu-id="7b92e-162">Brasilien – Juristische Personennummer (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="7b92e-162">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="7b92e-163">	Brasilien – Personalausweis (RG)</span><span class="sxs-lookup"><span data-stu-id="7b92e-163">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="7b92e-164">Kanadische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-164">Canada Bank Account Number</span></span>
- <span data-ttu-id="7b92e-165">Kanadische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-165">Canada Driver's License Number</span></span>
- <span data-ttu-id="7b92e-166">Kanadische Health Service-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-166">Canada Health Service Number</span></span>
- <span data-ttu-id="7b92e-167">Kanadische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-167">Canada Passport Number</span></span>
- <span data-ttu-id="7b92e-168">Kanadische Personal Health Identification-Nummer (PHIN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-168">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="7b92e-169">Kanadische Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-169">Canada Social Insurance Number</span></span>
- <span data-ttu-id="7b92e-170">	Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-170">Chile Identity Card Number</span></span>
- <span data-ttu-id="7b92e-171">	China (PRC) – Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-171">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="7b92e-172">Kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-172">Credit Card Number</span></span>
- <span data-ttu-id="7b92e-173">Kroatische ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-173">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="7b92e-174">Kroatische persönliche ID-Nummer (OIB)</span><span class="sxs-lookup"><span data-stu-id="7b92e-174">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="7b92e-175">Tschechische Persönliche Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-175">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="7b92e-176">Dänische persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-176">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="7b92e-177">Drug Enforcement Agency (DEA)-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-177">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="7b92e-178">EU-Debitkartennummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-178">EU Debit Card Number</span></span>
- <span data-ttu-id="7b92e-179">EU-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-179">EU Driver's License Number</span></span>  
- <span data-ttu-id="7b92e-180">Nationale EU-Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-180">EU National Identification Number</span></span>  
- <span data-ttu-id="7b92e-181">EU-Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-181">EU Passport Number</span></span>  
- <span data-ttu-id="7b92e-182">EU-Sozialversicherungsnummer (SSN) oder Äquivalent-ID</span><span class="sxs-lookup"><span data-stu-id="7b92e-182">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="7b92e-183">EU Tax Identification Number (TIN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-183">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="7b92e-184">Nationale finnische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-184">Finland National ID</span></span>
- <span data-ttu-id="7b92e-185">Finnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-185">Finland Passport Number</span></span>
- <span data-ttu-id="7b92e-186">Französische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-186">France Driver's License Number</span></span>
- <span data-ttu-id="7b92e-187">Französischer Personalausweis (Carte Nationale d'Identité, CNI)</span><span class="sxs-lookup"><span data-stu-id="7b92e-187">France National ID Card (CNI)</span></span>
- <span data-ttu-id="7b92e-188">Französische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-188">France Passport Number</span></span>
- <span data-ttu-id="7b92e-189">Französische Sozialversicherungsnummer (INSEE)</span><span class="sxs-lookup"><span data-stu-id="7b92e-189">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="7b92e-190">Deutsche Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-190">German Driver's License Number</span></span>
- <span data-ttu-id="7b92e-191">Deutsche Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-191">German Passport Number</span></span>
- <span data-ttu-id="7b92e-192">Deutsche Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-192">Germany Identity Card Number</span></span>
- <span data-ttu-id="7b92e-193">Nationale griechische ID-Karte</span><span class="sxs-lookup"><span data-stu-id="7b92e-193">Greece National ID Card</span></span>  
- <span data-ttu-id="7b92e-194">Hongkong (HKID) - Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-194">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="7b92e-195">Indien – Permanente Kontonummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-195">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="7b92e-196">Indien - Eindeutige Identifikationsnummer (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="7b92e-196">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="7b92e-197">Indonesien – Perosonalausweisnummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="7b92e-197">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="7b92e-198">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-198">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="7b92e-199">International Classification of Diseases (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="7b92e-199">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="7b92e-200">International Classification of Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="7b92e-200">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="7b92e-201">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="7b92e-201">IP Address</span></span>
- <span data-ttu-id="7b92e-202">Irische PPS-Nummer (Personal Public Service)</span><span class="sxs-lookup"><span data-stu-id="7b92e-202">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="7b92e-203">Israelische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-203">Israel Bank Account Number</span></span>
- <span data-ttu-id="7b92e-204">Israelische Ausweis-ID</span><span class="sxs-lookup"><span data-stu-id="7b92e-204">Israel National ID</span></span>
- <span data-ttu-id="7b92e-205">Italienische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-205">Italy Driver's License Number</span></span>
- <span data-ttu-id="7b92e-206">Japanische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-206">Japan Bank Account Number</span></span>
- <span data-ttu-id="7b92e-207">Japanische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-207">Japan Driver's License Number</span></span>
- <span data-ttu-id="7b92e-208">Japanische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-208">Japan Passport Number</span></span>
- <span data-ttu-id="7b92e-209">Japanische Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-209">Japan Resident Registration Number</span></span>
- <span data-ttu-id="7b92e-210">Japanische Sozialversicherungsnummer (SIN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-210">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="7b92e-211">Japanische Wohnsitzkartennummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-211">Japanese Residence Card Number</span></span>
- <span data-ttu-id="7b92e-212">Malaysia Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-212">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="7b92e-213">Nummer des niederländischen Citizen's Service (BSN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-213">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="7b92e-214">Neuseeländische Gesundheitsministeriumsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-214">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="7b92e-215">Norwegische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-215">Norway Identity Number</span></span>  
- <span data-ttu-id="7b92e-216">Philippinen – Vereinheitlichte Mehrzweck-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-216">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="7b92e-217">Polnische Identitätskarte</span><span class="sxs-lookup"><span data-stu-id="7b92e-217">Poland Identity Card</span></span>
- <span data-ttu-id="7b92e-218">Nationale polnische ID-Nummer (PESEL)</span><span class="sxs-lookup"><span data-stu-id="7b92e-218">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="7b92e-219">Polnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-219">Poland Passport</span></span>
- <span data-ttu-id="7b92e-220">Portugiesische ID-Kartennummer (Citizen Card)</span><span class="sxs-lookup"><span data-stu-id="7b92e-220">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="7b92e-221">Saudi-Arabische Ausweisnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-221">Saudi Arabia National ID</span></span>
- <span data-ttu-id="7b92e-222">Singapur – National Registration Identity Card-Nummer (NRIC)</span><span class="sxs-lookup"><span data-stu-id="7b92e-222">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="7b92e-223">Südafrika – Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-223">South Africa Identification Number</span></span>  
- <span data-ttu-id="7b92e-224">Südkorea – Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-224">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="7b92e-225">Spanische Sozialversicherungsnummer (SSN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-225">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="7b92e-226">SQL Server Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7b92e-226">SQL Server Connection String</span></span>  
- <span data-ttu-id="7b92e-227">Nationale schwedische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-227">Sweden National ID</span></span>
- <span data-ttu-id="7b92e-228">Schwedische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-228">Sweden Passport Number</span></span>
- <span data-ttu-id="7b92e-229">SWIFT-Code</span><span class="sxs-lookup"><span data-stu-id="7b92e-229">SWIFT Code</span></span>
- <span data-ttu-id="7b92e-230">Taiwanesicher Personalausweis</span><span class="sxs-lookup"><span data-stu-id="7b92e-230">Taiwan National ID</span></span>
- <span data-ttu-id="7b92e-231">	Taiwan – Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-231">Taiwan Passport Number</span></span>
- <span data-ttu-id="7b92e-232">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="7b92e-232">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="7b92e-233">Thai Population Identification Code</span><span class="sxs-lookup"><span data-stu-id="7b92e-233">Thai Population Identification Code</span></span>
- <span data-ttu-id="7b92e-234">Nationale Identifikationsnummer der Türkei</span><span class="sxs-lookup"><span data-stu-id="7b92e-234">Turkish National Identification number</span></span>
- <span data-ttu-id="7b92e-p103">Vereinigtes Königreich – Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="7b92e-p104">Vereinigtes Königreich – Wählerverzeichnisnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="7b92e-p105">UK-Gesundheitsdienstnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="7b92e-p106">UK-Sozialversicherungsnummer (National Insurance Number, NINO)</span><span class="sxs-lookup"><span data-stu-id="7b92e-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="7b92e-243">USA/Vereinigtes Königreich</span><span class="sxs-lookup"><span data-stu-id="7b92e-243">U.S. / U.K.</span></span> <span data-ttu-id="7b92e-244">Passport Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-244">Passport Number</span></span>
- <span data-ttu-id="7b92e-245">US-Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-245">U.S. Bank Account Number</span></span>
- <span data-ttu-id="7b92e-246">US-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-246">U.S. Driver's License Number</span></span>
- <span data-ttu-id="7b92e-247">US-Steueridentifikationsnummer (ITIN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-247">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="7b92e-248">US-Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-248">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="7b92e-249">Beachten Sie, dass benutzerdefinierte Typen vertraulicher Informationen zusätzlich zu den oben genannten typen für vertrauliche Informationen auch für DLP-Richtlinientipps unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7b92e-249">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="7b92e-250">Verhinderung von Datenverlust auf Endpunktgeräten unterstützt Richtlinientipps nur für einige typen von vertraulichen Informationen</span><span class="sxs-lookup"><span data-stu-id="7b92e-250">Data Loss Prevention on endpoint devices supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="7b92e-251">Die Liste der sofort verwendeten Typen vertraulicher Informationen, die in Dokumenten erkannt werden, die sich auf Endpunktgeräten befinden, sind folgende:</span><span class="sxs-lookup"><span data-stu-id="7b92e-251">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="7b92e-252">ABA Routing Number (US-Bankleitzahl)</span><span class="sxs-lookup"><span data-stu-id="7b92e-252">ABA Routing Number</span></span> 
- <span data-ttu-id="7b92e-253">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-253">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="7b92e-254">Australische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-254">Australia Bank Account Number</span></span> 
- <span data-ttu-id="7b92e-255">Australische Medical Account-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-255">Australia Medical Account Number</span></span> 
- <span data-ttu-id="7b92e-256">Australische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-256">Australia Passport Number</span></span> 
- <span data-ttu-id="7b92e-257">Australische Steuernummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-257">Australia Tax File Number</span></span> 
- <span data-ttu-id="7b92e-258">Australische Geschäftsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-258">Australian Business Number</span></span> 
- <span data-ttu-id="7b92e-259">Australische Firmennummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-259">Australian Company Number</span></span> 
- <span data-ttu-id="7b92e-260">Austria Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-260">Austria Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-261">Austria Identity Card</span><span class="sxs-lookup"><span data-stu-id="7b92e-261">Austria Identity Card</span></span> 
- <span data-ttu-id="7b92e-262">Austria Passport Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-262">Austria Passport Number</span></span> 
- <span data-ttu-id="7b92e-263">Österreich Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-263">Austria Social Security Number</span></span> 
- <span data-ttu-id="7b92e-264">Steueridentifikationsnummer für Österreich</span><span class="sxs-lookup"><span data-stu-id="7b92e-264">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="7b92e-265">Austria Value Added Tax (VAT) Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-265">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="7b92e-266">Azure DocumentDB-Authentifizierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="7b92e-266">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="7b92e-267">Azure IAAS Database Connection String und Azure SQL Connection String</span><span class="sxs-lookup"><span data-stu-id="7b92e-267">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="7b92e-268">Azure IoT-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7b92e-268">Azure IoT Connection String</span></span> 
- <span data-ttu-id="7b92e-269">Azure Publish Setting Password</span><span class="sxs-lookup"><span data-stu-id="7b92e-269">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="7b92e-270">Azure Redis Cache Connection String</span><span class="sxs-lookup"><span data-stu-id="7b92e-270">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="7b92e-271">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="7b92e-271">Azure SAS</span></span> 
- <span data-ttu-id="7b92e-272">Azure Service Bus Connection String</span><span class="sxs-lookup"><span data-stu-id="7b92e-272">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="7b92e-273">Azure Storage Account Key</span><span class="sxs-lookup"><span data-stu-id="7b92e-273">Azure Storage Account Key</span></span> 
- <span data-ttu-id="7b92e-274">Azure Storage Account Key (Generisch)</span><span class="sxs-lookup"><span data-stu-id="7b92e-274">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="7b92e-275">Belgische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-275">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-276">Nationale belgische Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-276">Belgium National Number</span></span> 
- <span data-ttu-id="7b92e-277">Belgische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-277">Belgium Passport Number</span></span> 
- <span data-ttu-id="7b92e-278">Belgische Umsatzsteuernummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-278">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="7b92e-279">Brazil CPF Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-279">Brazil CPF Number</span></span> 
- <span data-ttu-id="7b92e-280">Brasilien – Juristische Personennummer (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="7b92e-280">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="7b92e-281">	Brasilien – Personalausweis (RG)</span><span class="sxs-lookup"><span data-stu-id="7b92e-281">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="7b92e-282">Kennzeichen des Bulgarien-Führerscheins</span><span class="sxs-lookup"><span data-stu-id="7b92e-282">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-283">Bulgarien Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-283">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="7b92e-284">Uniform Civil Number (Bulgarien)</span><span class="sxs-lookup"><span data-stu-id="7b92e-284">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="7b92e-285">Kanadische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-285">Canada Bank Account Number</span></span> 
- <span data-ttu-id="7b92e-286">Kanadische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-286">Canada Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-287">Kanadische Health Service-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-287">Canada Health Service Number</span></span> 
- <span data-ttu-id="7b92e-288">Kanadische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-288">Canada Passport Number</span></span> 
- <span data-ttu-id="7b92e-289">Kanadische Personal Health Identification-Nummer (PHIN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-289">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="7b92e-290">Kanadische Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-290">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="7b92e-291">	Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-291">Chile Identity Card Number</span></span> 
- <span data-ttu-id="7b92e-292">	China (PRC) – Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-292">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="7b92e-293">Kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-293">Credit Card Number</span></span> 
- <span data-ttu-id="7b92e-294">Kroatische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-294">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-295">Kroatische ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-295">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="7b92e-296">Kroatische Nationale ID-Kartennummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-296">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="7b92e-297">Kroatische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-297">Croatia Passport Number</span></span> 
- <span data-ttu-id="7b92e-298">Kroatische persönliche ID-Nummer (OIB)</span><span class="sxs-lookup"><span data-stu-id="7b92e-298">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="7b92e-299">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span><span class="sxs-lookup"><span data-stu-id="7b92e-299">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="7b92e-300">CSCAN-GENERAL0140 Allgemeiner symmetrischer Schlüssel</span><span class="sxs-lookup"><span data-stu-id="7b92e-300">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="7b92e-301">Zyprische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-301">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-302">Identitätskarte für Zypern</span><span class="sxs-lookup"><span data-stu-id="7b92e-302">Cyprus Identity Card</span></span> 
- <span data-ttu-id="7b92e-303">Reisepassnummer für Zypern</span><span class="sxs-lookup"><span data-stu-id="7b92e-303">Cyprus Passport Number</span></span> 
- <span data-ttu-id="7b92e-304">Steueridentifikationsnummer für Zypern</span><span class="sxs-lookup"><span data-stu-id="7b92e-304">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="7b92e-305">Tschechische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-305">Czech Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-306">Tschechische Persönliche Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-306">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="7b92e-307">Tschechische Republik Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-307">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="7b92e-308">Dänische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-308">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-309">Dänische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-309">Denmark Passport Number</span></span> 
- <span data-ttu-id="7b92e-310">Dänische persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-310">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="7b92e-311">Drug Enforcement Agency (DEA)-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-311">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="7b92e-312">Estonia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-312">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-313">Estonia Passport Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-313">Estonia Passport Number</span></span> 
- <span data-ttu-id="7b92e-314">Estonia Personal Identification Code</span><span class="sxs-lookup"><span data-stu-id="7b92e-314">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="7b92e-315">EU-Debitkartennummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-315">EU Debit Card Number</span></span> 
- <span data-ttu-id="7b92e-316">EU-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-316">EU Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-317">Nationale EU-Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-317">EU National Identification Number</span></span> 
- <span data-ttu-id="7b92e-318">EU-Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-318">EU Passport Number</span></span> 
- <span data-ttu-id="7b92e-319">EU-Sozialversicherungsnummer (SSN) oder Äquivalent-ID</span><span class="sxs-lookup"><span data-stu-id="7b92e-319">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="7b92e-320">EU Tax Identification Number (TIN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-320">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="7b92e-321">Finland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-321">Finland Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-322">Finnland Europäische Krankenversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-322">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="7b92e-323">Nationale finnische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-323">Finland National ID</span></span> 
- <span data-ttu-id="7b92e-324">Finnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-324">Finland Passport Number</span></span> 
- <span data-ttu-id="7b92e-325">Französische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-325">France Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-326">Französische Krankenversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-326">France Health Insurance Number</span></span> 
- <span data-ttu-id="7b92e-327">Französischer Personalausweis (Carte Nationale d'Identité, CNI)</span><span class="sxs-lookup"><span data-stu-id="7b92e-327">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="7b92e-328">Französische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-328">France Passport Number</span></span> 
- <span data-ttu-id="7b92e-329">Französische Sozialversicherungsnummer (INSEE)</span><span class="sxs-lookup"><span data-stu-id="7b92e-329">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="7b92e-330">Französische Steueridentifikationsnummer (numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="7b92e-330">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="7b92e-331">Französische Umsatzsteuernummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-331">France Value Added Tax Number</span></span> 
- <span data-ttu-id="7b92e-332">Deutsche Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-332">German Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-333">Deutsche Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-333">German Passport Number</span></span> 
- <span data-ttu-id="7b92e-334">Deutsche Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-334">Germany Identity Card Number</span></span> 
- <span data-ttu-id="7b92e-335">Deutsche Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-335">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="7b92e-336">Deutsche Umsatzsteuernummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-336">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="7b92e-337">Führerscheinnummer für Griechenland</span><span class="sxs-lookup"><span data-stu-id="7b92e-337">Greece Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-338">Nationale griechische ID-Karte</span><span class="sxs-lookup"><span data-stu-id="7b92e-338">Greece National ID Card</span></span> 
- <span data-ttu-id="7b92e-339">Griechenland Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-339">Greece Passport Number</span></span> 
- <span data-ttu-id="7b92e-340">Griechenland Sozialversicherungsnummer (AMKA)</span><span class="sxs-lookup"><span data-stu-id="7b92e-340">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="7b92e-341">Griechische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-341">Greek Tax identification Number</span></span> 
- <span data-ttu-id="7b92e-342">Hongkong (HKID) - Personalausweisnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-342">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="7b92e-343">Ungarische Sozialversicherungsnummer (TAJ)</span><span class="sxs-lookup"><span data-stu-id="7b92e-343">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="7b92e-344">Mehrwertsteuernummer für Ungarn</span><span class="sxs-lookup"><span data-stu-id="7b92e-344">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="7b92e-345">Kennzeichen des Ungarn-Führerscheins</span><span class="sxs-lookup"><span data-stu-id="7b92e-345">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-346">Ungarn Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-346">Hungary Passport Number</span></span> 
- <span data-ttu-id="7b92e-347">Ungarn Persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-347">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="7b92e-348">Ungarn Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-348">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="7b92e-349">Indien – Permanente Kontonummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-349">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="7b92e-350">Indien - Eindeutige Identifikationsnummer (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="7b92e-350">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="7b92e-351">Indonesien – Perosonalausweisnummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="7b92e-351">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="7b92e-352">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-352">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="7b92e-353">International Classification of Diseases (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="7b92e-353">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="7b92e-354">International Classification of Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="7b92e-354">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="7b92e-355">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="7b92e-355">IP Address</span></span> 
- <span data-ttu-id="7b92e-356">Ireland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-356">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-357">Irland Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-357">Ireland Passport Number</span></span> 
- <span data-ttu-id="7b92e-358">Irische PPS-Nummer (Personal Public Service)</span><span class="sxs-lookup"><span data-stu-id="7b92e-358">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="7b92e-359">Israelische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-359">Israel Bank Account Number</span></span> 
- <span data-ttu-id="7b92e-360">Israelische Ausweis-ID</span><span class="sxs-lookup"><span data-stu-id="7b92e-360">Israel National ID</span></span> 
- <span data-ttu-id="7b92e-361">Italienische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-361">Italy Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-362">Steuercode für Italien</span><span class="sxs-lookup"><span data-stu-id="7b92e-362">Italy Fiscal Code</span></span> 
- <span data-ttu-id="7b92e-363">Italienische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-363">Italy Passport Number</span></span> 
- <span data-ttu-id="7b92e-364">Italienische Mehrwertsteuernummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-364">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="7b92e-365">Japanische Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-365">Japan Bank Account Number</span></span> 
- <span data-ttu-id="7b92e-366">Japanische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-366">Japan Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-367">Japanische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-367">Japan Passport Number</span></span> 
- <span data-ttu-id="7b92e-368">Japanische Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-368">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="7b92e-369">Japanische Sozialversicherungsnummer (SIN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-369">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="7b92e-370">Japanische My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="7b92e-370">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="7b92e-371">Japanisch My Number Personal</span><span class="sxs-lookup"><span data-stu-id="7b92e-371">Japanese My Number Personal</span></span> 
- <span data-ttu-id="7b92e-372">Japanische Wohnsitzkartennummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-372">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="7b92e-373">Latvia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-373">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-374">Latvia Passport Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-374">Latvia Passport Number</span></span> 
- <span data-ttu-id="7b92e-375">Persönlichen Code für Lettland</span><span class="sxs-lookup"><span data-stu-id="7b92e-375">Latvia Personal Code</span></span> 
- <span data-ttu-id="7b92e-376">Lizenznummer des Litauen-Führerscheins</span><span class="sxs-lookup"><span data-stu-id="7b92e-376">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-377">Reisepassnummer für Litauen</span><span class="sxs-lookup"><span data-stu-id="7b92e-377">Lithuania Passport Number</span></span> 
- <span data-ttu-id="7b92e-378">Persönlichen Code für Litauen</span><span class="sxs-lookup"><span data-stu-id="7b92e-378">Lithuania Personal Code</span></span> 
- <span data-ttu-id="7b92e-379">LuxemburgEr Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-379">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-380">Nationale Identifikationsnummer (natürliche Personen)</span><span class="sxs-lookup"><span data-stu-id="7b92e-380">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="7b92e-381">Nationale Identifikationsnummer (nicht natürliche Personen)</span><span class="sxs-lookup"><span data-stu-id="7b92e-381">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="7b92e-382">Luxemburg Passport Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-382">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="7b92e-383">Malaysia Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-383">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="7b92e-384">Malta Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-384">Malta Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-385">Malta Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-385">Malta Identity Card Number</span></span> 
- <span data-ttu-id="7b92e-386">Malta Passport Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-386">Malta Passport Number</span></span> 
- <span data-ttu-id="7b92e-387">Malta Steuer-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-387">Malta Tax ID Number</span></span> 
- <span data-ttu-id="7b92e-388">Nummer des niederländischen Citizen's Service (BSN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-388">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="7b92e-389">Niederländische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-389">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-390">Niederländische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-390">Netherlands Passport Number</span></span> 
- <span data-ttu-id="7b92e-391">Niederländische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-391">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="7b92e-392">Niederländische Umsatzsteuernummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-392">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="7b92e-393">Bankkontonummer für Neuseeland</span><span class="sxs-lookup"><span data-stu-id="7b92e-393">New Zealand bank account number</span></span> 
- <span data-ttu-id="7b92e-394">New Zealand Driver License Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-394">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="7b92e-395">New Zealand Inland Revenue Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-395">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="7b92e-396">Neuseeländische Gesundheitsministeriumsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-396">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="7b92e-397">New Zealand Social Welfare Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-397">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="7b92e-398">Norwegische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-398">Norway Identity Number</span></span> 
- <span data-ttu-id="7b92e-399">Philippinen – Vereinheitlichte Mehrzweck-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-399">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="7b92e-400">Polnische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-400">Poland Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-401">Polnische Identitätskarte</span><span class="sxs-lookup"><span data-stu-id="7b92e-401">Poland Identity Card</span></span> 
- <span data-ttu-id="7b92e-402">Nationale polnische ID-Nummer (PESEL)</span><span class="sxs-lookup"><span data-stu-id="7b92e-402">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="7b92e-403">Polnische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-403">Poland Passport</span></span> 
- <span data-ttu-id="7b92e-404">Polnische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-404">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="7b92e-405">Polnische REGON-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-405">Polish REGON Number</span></span> 
- <span data-ttu-id="7b92e-406">Portugiesische ID-Kartennummer (Citizen Card)</span><span class="sxs-lookup"><span data-stu-id="7b92e-406">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="7b92e-407">Portugal Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-407">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-408">Portugal Passport Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-408">Portugal Passport Number</span></span> 
- <span data-ttu-id="7b92e-409">Steueridentifikationsnummer für Portugal</span><span class="sxs-lookup"><span data-stu-id="7b92e-409">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="7b92e-410">Romania Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-410">Romania Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-411">Rumänien Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-411">Romania Passport Number</span></span> 
- <span data-ttu-id="7b92e-412">Rumänien – Persönlicher numerischer Code (CNP)</span><span class="sxs-lookup"><span data-stu-id="7b92e-412">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="7b92e-413">Russische Reisepassnummer (Inland)</span><span class="sxs-lookup"><span data-stu-id="7b92e-413">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="7b92e-414">Russische Reisepassnummer (International)</span><span class="sxs-lookup"><span data-stu-id="7b92e-414">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="7b92e-415">Saudi-Arabische Ausweisnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-415">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="7b92e-416">Singapur – National Registration Identity Card-Nummer (NRIC)</span><span class="sxs-lookup"><span data-stu-id="7b92e-416">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="7b92e-417">Slovakia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-417">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-418">Slowakei Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-418">Slovakia Passport Number</span></span> 
- <span data-ttu-id="7b92e-419">Persönliche Nummer der Slowakei</span><span class="sxs-lookup"><span data-stu-id="7b92e-419">Slovakia Personal Number</span></span> 
- <span data-ttu-id="7b92e-420">Slovenia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-420">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-421">Slowenien Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-421">Slovenia Passport Number</span></span> 
- <span data-ttu-id="7b92e-422">Slowenien Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-422">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="7b92e-423">Slowenien Eindeutige Master Citizen Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-423">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="7b92e-424">Südafrika – Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-424">South Africa Identification Number</span></span> 
- <span data-ttu-id="7b92e-425">Südkorea – Einwohnerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-425">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="7b92e-426">Spanien DNI</span><span class="sxs-lookup"><span data-stu-id="7b92e-426">Spain DNI</span></span> 
- <span data-ttu-id="7b92e-427">Spain Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-427">Spain Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-428">Spanische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-428">Spain Passport Number</span></span> 
- <span data-ttu-id="7b92e-429">Spanische Sozialversicherungsnummer (SSN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-429">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="7b92e-430">Spanien Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-430">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="7b92e-431">SQL Server Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7b92e-431">SQL Server Connection String</span></span> 
- <span data-ttu-id="7b92e-432">Schwedische Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-432">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-433">Nationale schwedische ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-433">Sweden National ID</span></span> 
- <span data-ttu-id="7b92e-434">Schwedische Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-434">Sweden Passport Number</span></span> 
- <span data-ttu-id="7b92e-435">Steueridentifikationsnummer für Schweden</span><span class="sxs-lookup"><span data-stu-id="7b92e-435">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="7b92e-436">SWIFT-Code</span><span class="sxs-lookup"><span data-stu-id="7b92e-436">SWIFT Code</span></span> 
- <span data-ttu-id="7b92e-437">Swiss Social Security Number AHV</span><span class="sxs-lookup"><span data-stu-id="7b92e-437">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="7b92e-438">Taiwanesicher Personalausweis</span><span class="sxs-lookup"><span data-stu-id="7b92e-438">Taiwan National ID</span></span> 
- <span data-ttu-id="7b92e-439">	Taiwan – Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-439">Taiwan Passport Number</span></span> 
- <span data-ttu-id="7b92e-440">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="7b92e-440">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="7b92e-441">Thai Population Identification Code</span><span class="sxs-lookup"><span data-stu-id="7b92e-441">Thai Population Identification Code</span></span> 
- <span data-ttu-id="7b92e-442">Nationale Identifikationsnummer der Türkei</span><span class="sxs-lookup"><span data-stu-id="7b92e-442">Turkish National Identification number</span></span> 
- <span data-ttu-id="7b92e-p108">Vereinigtes Königreich – Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-p109">Vereinigtes Königreich – Wählerverzeichnisnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="7b92e-p110">UK-Gesundheitsdienstnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="7b92e-p111">UK-Sozialversicherungsnummer (National Insurance Number, NINO)</span><span class="sxs-lookup"><span data-stu-id="7b92e-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="7b92e-451">Vereinigtes Königreich</span><span class="sxs-lookup"><span data-stu-id="7b92e-451">U.K.</span></span> <span data-ttu-id="7b92e-452">Eindeutige Steuernummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-452">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="7b92e-453">USA/Vereinigtes Königreich</span><span class="sxs-lookup"><span data-stu-id="7b92e-453">U.S. / U.K.</span></span> <span data-ttu-id="7b92e-454">Passport Number</span><span class="sxs-lookup"><span data-stu-id="7b92e-454">Passport Number</span></span> 
- <span data-ttu-id="7b92e-455">US-Bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-455">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="7b92e-456">US-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-456">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="7b92e-457">US-Steueridentifikationsnummer (ITIN)</span><span class="sxs-lookup"><span data-stu-id="7b92e-457">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="7b92e-458">US-Sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="7b92e-458">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="7b92e-459">Ukraine Passport Number (Inland)</span><span class="sxs-lookup"><span data-stu-id="7b92e-459">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="7b92e-460">Ukraine Passport Number (International)</span><span class="sxs-lookup"><span data-stu-id="7b92e-460">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="7b92e-461">Bitte beachten Sie, dass zusätzlich zu den oben genannten sofort verwendeten Typen vertraulicher Informationen auch benutzerdefinierte Typen vertraulicher Informationen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="7b92e-461">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="7b92e-462">Support matrix for DLP policy tips across Microsoft apps</span><span class="sxs-lookup"><span data-stu-id="7b92e-462">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="7b92e-463">**App und Plattform**</span><span class="sxs-lookup"><span data-stu-id="7b92e-463">**App and platform**</span></span>|<span data-ttu-id="7b92e-464">**Unterstützung von DLP-Richtlinientipps**</span><span class="sxs-lookup"><span data-stu-id="7b92e-464">**DLP policy tip support**</span></span>|<span data-ttu-id="7b92e-465">**Unterstützte Typen vertraulicher Informationen**</span><span class="sxs-lookup"><span data-stu-id="7b92e-465">**Sensitive information types supported**</span></span>|<span data-ttu-id="7b92e-466">**Unterstützte Prädikate und Aktionen**</span><span class="sxs-lookup"><span data-stu-id="7b92e-466">**Predicates and actions supported**</span></span>|<span data-ttu-id="7b92e-467">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="7b92e-467">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="7b92e-468">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="7b92e-468">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="7b92e-469">Alle</span><span class="sxs-lookup"><span data-stu-id="7b92e-469">All</span></span>|<span data-ttu-id="7b92e-470">Subset</span><span class="sxs-lookup"><span data-stu-id="7b92e-470">Subset</span></span>|<span data-ttu-id="7b92e-471">Siehe [Hinweise zu Richtlinientipps zur](#data-loss-prevention-policy-tips-reference) Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="7b92e-471">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="7b92e-472">**Outlook Win32 (Outlook 2013 und darüber hinaus)**</span><span class="sxs-lookup"><span data-stu-id="7b92e-472">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="7b92e-473">Subset</span><span class="sxs-lookup"><span data-stu-id="7b92e-473">Subset</span></span>|<span data-ttu-id="7b92e-474">Subset</span><span class="sxs-lookup"><span data-stu-id="7b92e-474">Subset</span></span>|<span data-ttu-id="7b92e-475">Unter Outlook 2013 und höher finden Sie Richtlinientipps für nur einige Bedingungen und Ausnahmen sowie Unterstützung für [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) und höher und Office-Apps auf Desktop mit Richtlinientipps für nur einige typen vertraulicher Informationen. Weitere Informationen zur Unterstützung vertraulicher Informationstypen sowie von DLP-Bedingungen und -Aktionen, die für die Anzeige von DLP-Richtlinientipps in Outlook Win32 unterstützt werden, finden Sie unter Outlook [2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) und höher.</span><span class="sxs-lookup"><span data-stu-id="7b92e-475">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="7b92e-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="7b92e-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="7b92e-477">Keine</span><span class="sxs-lookup"><span data-stu-id="7b92e-477">None</span></span>|<span data-ttu-id="7b92e-478">Keine</span><span class="sxs-lookup"><span data-stu-id="7b92e-478">None</span></span>|<span data-ttu-id="7b92e-479">DLP-Richtlinientipps werden auf Outlook mobilen Geräten nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="7b92e-479">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="7b92e-480">**Sharepoint Online/One Drive for Business Web Client**</span><span class="sxs-lookup"><span data-stu-id="7b92e-480">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="7b92e-481">Alle</span><span class="sxs-lookup"><span data-stu-id="7b92e-481">All</span></span>|<span data-ttu-id="7b92e-482">Alle SPO/ODB-Prädikate und -Aktionen in DLP</span><span class="sxs-lookup"><span data-stu-id="7b92e-482">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="7b92e-483">**Sharepoint Win32/ One Drive for Business Win32-Client**</span><span class="sxs-lookup"><span data-stu-id="7b92e-483">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="7b92e-484">Keine</span><span class="sxs-lookup"><span data-stu-id="7b92e-484">None</span></span>|<span data-ttu-id="7b92e-485">Keine</span><span class="sxs-lookup"><span data-stu-id="7b92e-485">None</span></span>|<span data-ttu-id="7b92e-486">#A0 werden in Sharepoint- oder OneDrive-Desktopclient-Apps nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="7b92e-486">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="7b92e-487">**Word, Excel, PowerPoint Web Client**</span><span class="sxs-lookup"><span data-stu-id="7b92e-487">**Word, Excel, PowerPoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="7b92e-488">Alle</span><span class="sxs-lookup"><span data-stu-id="7b92e-488">All</span></span>|<span data-ttu-id="7b92e-489">Alle SPO/ODB-Prädikate und -Aktionen in DLP</span><span class="sxs-lookup"><span data-stu-id="7b92e-489">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="7b92e-490">Der Tipp für die DLP-Richtlinie wird unterstützt, wenn das Dokument in spo- oder ODB-Web-App gehostet wird und die DLP-Richtlinie bereits gestempelt ist.</span><span class="sxs-lookup"><span data-stu-id="7b92e-490">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="7b92e-491">**Word, Excel, PowerPoint Mobile Client**</span><span class="sxs-lookup"><span data-stu-id="7b92e-491">**Word, Excel, PowerPoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="7b92e-492">Keine</span><span class="sxs-lookup"><span data-stu-id="7b92e-492">None</span></span>|<span data-ttu-id="7b92e-493">Keine</span><span class="sxs-lookup"><span data-stu-id="7b92e-493">None</span></span>|<span data-ttu-id="7b92e-494">DLP-Richtlinientipps werden in mobilen Apps für Office nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7b92e-494">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="7b92e-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="7b92e-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="7b92e-496">Alle</span><span class="sxs-lookup"><span data-stu-id="7b92e-496">All</span></span>|<span data-ttu-id="7b92e-497">Alle Teams-Prädikate in der DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="7b92e-497">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="7b92e-498">Richtlinientipps werden angezeigt, wenn eine Nachricht mit "Diese Nachricht wurde gekennzeichnet" gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="7b92e-498">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="7b92e-499">Was kann ich tun?"</span><span class="sxs-lookup"><span data-stu-id="7b92e-499">What can I do?”</span></span> <span data-ttu-id="7b92e-500">Wenn der Benutzer auf den Link klickt, kann er die erkannten Typen vertraulicher Informationen überprüfen und ein Problem außer Kraft setzen oder melden, wenn dies vom Administrator zulässig ist. Beachten Sie, dass keine Richtlinientipps für Dateien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7b92e-500">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="7b92e-501">Wenn der Empfänger versucht, auf das Dokument zu zugreifen, erhält er möglicherweise zugriff verweigert, wenn er nicht zugelassen ist.</span><span class="sxs-lookup"><span data-stu-id="7b92e-501">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="7b92e-502">**Win32-Endpunktgeräte**</span><span class="sxs-lookup"><span data-stu-id="7b92e-502">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="7b92e-503">Subset</span><span class="sxs-lookup"><span data-stu-id="7b92e-503">Subset</span></span>|<span data-ttu-id="7b92e-504">Alle Endpunkt-DLP-Prädikate und -Aktionen in der DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="7b92e-504">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="7b92e-505">Weitere [Informationen finden Sie unter Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types.](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="7b92e-505">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="7b92e-506">**Mac-Geräte**</span><span class="sxs-lookup"><span data-stu-id="7b92e-506">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="7b92e-507">Keine</span><span class="sxs-lookup"><span data-stu-id="7b92e-507">None</span></span>|<span data-ttu-id="7b92e-508">Keine</span><span class="sxs-lookup"><span data-stu-id="7b92e-508">None</span></span>|<span data-ttu-id="7b92e-509">Richtlinien zur Verhinderung von Datenverlust sind heute auf Mac-Geräten nicht durchsetzbar</span><span class="sxs-lookup"><span data-stu-id="7b92e-509">Data loss prevention policies are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="7b92e-510">**Cloud-Apps von Drittanbietern**</span><span class="sxs-lookup"><span data-stu-id="7b92e-510">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="7b92e-511">Keine</span><span class="sxs-lookup"><span data-stu-id="7b92e-511">None</span></span>|<span data-ttu-id="7b92e-512">Keine</span><span class="sxs-lookup"><span data-stu-id="7b92e-512">None</span></span>|<span data-ttu-id="7b92e-513">Richtlinientipps zur Verhinderung von Datenverlust werden in Cloud-Apps von Drittanbietern nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7b92e-513">Data Loss Prevention policy tips are not supported on 3rd party cloud apps</span></span>|
|<span data-ttu-id="7b92e-514">**On-Prem**</span><span class="sxs-lookup"><span data-stu-id="7b92e-514">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="7b92e-515">Keine</span><span class="sxs-lookup"><span data-stu-id="7b92e-515">None</span></span>|<span data-ttu-id="7b92e-516">Keine</span><span class="sxs-lookup"><span data-stu-id="7b92e-516">None</span></span>||
|<span data-ttu-id="7b92e-517">**Word, Excel, PowerPoint Win32 Client**</span><span class="sxs-lookup"><span data-stu-id="7b92e-517">**Word, Excel, PowerPoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="7b92e-518">Subset</span><span class="sxs-lookup"><span data-stu-id="7b92e-518">Subset</span></span>|<span data-ttu-id="7b92e-519">Subset</span><span class="sxs-lookup"><span data-stu-id="7b92e-519">Subset</span></span>|<span data-ttu-id="7b92e-520">Informationen zur Liste der unterstützten Typen vertraulicher Informationen finden Sie unter Unterstützung von [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) und höher sowie unter Unterstützung von Office-Apps auf Desktop mit Richtlinientipps für nur einige Typen vertraulicher Informationen.</span><span class="sxs-lookup"><span data-stu-id="7b92e-520">Please see [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for the list of sensitive information types supported</span></span></br></br><span data-ttu-id="7b92e-521">Richtlinientipps für WXP-Client-Apps funktionieren für Dokumente, die auf Sharepoint Online- oder One Drive for Business-Websites gespeichert sind, für alle DLP-Richtlinien, die genau die folgende oder eine Teilmenge von Bedingungen oder Aktionen in der DLP-Richtlinie enthalten:</span><span class="sxs-lookup"><span data-stu-id="7b92e-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="7b92e-522">Inhalt enthält Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="7b92e-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="7b92e-523">Zugriffsbereich (Inhalt wird intern/extern freigegeben)</span><span class="sxs-lookup"><span data-stu-id="7b92e-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="7b92e-524">Benutzer benachrichtigen (Richtlinientipps/Benutzerbenachrichtigungen)</span><span class="sxs-lookup"><span data-stu-id="7b92e-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="7b92e-525">Blockieren von allen</span><span class="sxs-lookup"><span data-stu-id="7b92e-525">Block everyone</span></span></li><li><span data-ttu-id="7b92e-526">Schadensberichte</span><span class="sxs-lookup"><span data-stu-id="7b92e-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="7b92e-527">Wenn eine andere Bedingung oder Aktion vorhanden ist, wird der DLP-Richtlinientipp für diese Richtlinie nicht in den Desktop-Apps von Word, Excel oder PowerPoint angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7b92e-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span></br><span data-ttu-id="7b92e-528">Weitere [Informationen finden Sie unter Richtlinientipps in Excel, PowerPoint](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) und Word</span><span class="sxs-lookup"><span data-stu-id="7b92e-528">See [Policy tips in Excel, PowerPoint, and Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) for more details</span></span>|
||||||
