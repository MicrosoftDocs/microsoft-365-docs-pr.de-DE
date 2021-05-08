---
title: Einrichten von SPF zum Verhindern von Spoofing
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie ein DNS-Eintrag (Domain Name Service) für die Verwendung von SPF (Sender Policy Framework) mit Ihrer benutzerdefinierten Domäne in Office 365 aktualisiert wird.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d200c4cf17a3d42ddafca301fecbf18c249ac37
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245684"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="eda7c-103">Einrichten von SPF zum Verhindern von Spoofing</span><span class="sxs-lookup"><span data-stu-id="eda7c-103">Set up SPF to help prevent spoofing</span></span>

- [<span data-ttu-id="eda7c-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="eda7c-104">Prerequisites</span></span>](#prerequisites)
- [<span data-ttu-id="eda7c-105">Erstellen oder aktualisieren Sie Ihren SPF TXT-Eintrag</span><span class="sxs-lookup"><span data-stu-id="eda7c-105">Create or update your SPF TXT record</span></span>](#create-or-update-your-spf-txt-record)
- [<span data-ttu-id="eda7c-106">Wie kann ich Subdomänen behandeln?</span><span class="sxs-lookup"><span data-stu-id="eda7c-106">How to handle subdomains?</span></span>](#how-to-handle-subdomains)
- [<span data-ttu-id="eda7c-107">Problembehandlung von SPF</span><span class="sxs-lookup"><span data-stu-id="eda7c-107">Troubleshooting SPF</span></span>](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

<span data-ttu-id="eda7c-108">Dieser Artikel beschreibt, wie Sie einen DNS-Eintrag (Domain Name Service) für die Verwendung von SPF (Sender Policy Framework) -E-Mail-Authentifizierung mit Ihrer benutzerdefinierten Domäne in Office 365 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="eda7c-108">This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF)  email authentication with your custom domain in Office 365.</span></span>

<span data-ttu-id="eda7c-109">SPF hilft bei der *Validierung* ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden (also von dort kommen, wo sie sagen, dass sie kommen).</span><span class="sxs-lookup"><span data-stu-id="eda7c-109">SPF helps *validate* outbound email sent from your custom domain (is coming from who it says it is).</span></span> <span data-ttu-id="eda7c-110">Es ist ein erster Schritt bei der Einrichtung der gesamten empfohlenen E-Mail-Authentifizierungsmethoden von SPF, [DKIM](use-dkim-to-validate-outbound-email.md) und [DMARC](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="eda7c-110">It's a first step in setting up the full recommended email authentication methods of SPF, [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eda7c-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="eda7c-111">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eda7c-112">Wenn Sie ein **kleines Unternehmen** sind oder mit IP-Adressen oder DNS-Konfigurationen nicht vertraut sind, wenden Sie sich an Ihre Internet-Domänenregistrierungsstelle (z. B.</span><span class="sxs-lookup"><span data-stu-id="eda7c-112">If you are a **small business**, or are unfamiliar with IP addresses or DNS configuration, call your Internet domain registrar (ex.</span></span> <span data-ttu-id="eda7c-113">GoDaddy, Bluehost, web.com) und bitten Sie um Hilfe zur *DNS-Konfiguration von SPF* (und anderen E-Mail-Authentifizierungsmethoden).</span><span class="sxs-lookup"><span data-stu-id="eda7c-113">GoDaddy, Bluehost, web.com) & ask for help with *DNS configuration of SPF* (and any other email authentication method).</span></span> <p> <span data-ttu-id="eda7c-114">**Wenn Sie keine benutzerdefinierte URL verwenden** (und die für Office 365 verwendete URL auf **onmicrosoft.com** endet), wurde SPF bereits im Office 365-Dienst für Sie eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="eda7c-114">**If you don't use a custom URL** (and the URL used for Office 365 ends in **onmicrosoft.com**), SPF has already been set up for you in the Office 365 service.</span></span>

<span data-ttu-id="eda7c-115">Lassen Sie uns beginnen.</span><span class="sxs-lookup"><span data-stu-id="eda7c-115">Let's get started.</span></span>

<span data-ttu-id="eda7c-116">Der SPF TXT-Eintrag für Office 365 wird für alle benutzerdefinierten Domänen und Subdomänen in einem externen DNS erstellt.</span><span class="sxs-lookup"><span data-stu-id="eda7c-116">The SPF TXT record for Office 365 will be made in external DNS for any custom domains or subdomains.</span></span> <span data-ttu-id="eda7c-117">Sie benötigen einige Informationen, um den Datensatz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eda7c-117">You need some information to make the record.</span></span> <span data-ttu-id="eda7c-118">Sammeln Sie diese Informationen:</span><span class="sxs-lookup"><span data-stu-id="eda7c-118">Gather this information:</span></span>

- <span data-ttu-id="eda7c-119">Den SPF TXT-Eintrag für Ihre benutzerdefinierte Domäne (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="eda7c-119">The SPF TXT record for your custom domain, if one exists.</span></span> <span data-ttu-id="eda7c-120">Anweisungen finden Sie unter [Sammeln der zum Erstellen von Office 365-DNS-Einträgen erforderlichen Informationen](../../admin/get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="eda7c-120">For instructions, see [Gather the information you need to create Office 365 DNS records](../../admin/get-help-with-domains/information-for-dns-records.md).</span></span>

- <span data-ttu-id="eda7c-121">Gehen Sie zu Ihrem/Ihren Nachrichten-Server(n) und ermitteln Sie die externen IP-Adressen (die von allen lokalen Nachrichten-Servern benötigt werden).</span><span class="sxs-lookup"><span data-stu-id="eda7c-121">Go to your messaging server(s) and find out the External IP addresses (needed from all on-premises messaging servers).</span></span> <span data-ttu-id="eda7c-122">Beispiel: **131.107.2.200**.</span><span class="sxs-lookup"><span data-stu-id="eda7c-122">For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="eda7c-p106">Domänennamen für alle Domänen von Drittanbietern, die Sie in Ihren SPF TXT-Eintrag einschließen müssen. Einige Massen-E-Mail-Anbieter haben Unterdomänen für ihre Kunden eingerichtet. Das Unternehmen MailChimp hat beispielsweise **servers.mcsv.net** eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="eda7c-p106">Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="eda7c-126">Finden Sie heraus, welche Erzwingungsregel Sie für Ihren SPF TXT-Eintrag verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="eda7c-126">Figure out what enforcement rule you want to use for your SPF TXT record.</span></span> <span data-ttu-id="eda7c-127">Die Regel **-all** wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="eda7c-127">The **-all** rule is recommended.</span></span> <span data-ttu-id="eda7c-128">Weitere Informationen zu anderen Syntaxoptionen finden Sie unter [Syntax des SPF TXT-Eintrags für Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span><span class="sxs-lookup"><span data-stu-id="eda7c-128">For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eda7c-129">Für die Verwendung einer benutzerdefinierten Domäne erfordert Office 365, einen SPF (Sender Policy Framework) TXT-Eintrag Ihrem DNS-Eintrag hinzuzufügen, um Spoofing zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="eda7c-129">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing.</span></span>

## <a name="create-or-update-your-spf-txt-record"></a><span data-ttu-id="eda7c-130">Erstellen oder aktualisieren Sie Ihren SPF TXT-Eintrag</span><span class="sxs-lookup"><span data-stu-id="eda7c-130">Create or update your SPF TXT record</span></span>

1. <span data-ttu-id="eda7c-131">Machen Sie sich mit der SPF-Syntax in der folgenden Tabelle vertraut.</span><span class="sxs-lookup"><span data-stu-id="eda7c-131">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ****

   |<span data-ttu-id="eda7c-132">Element</span><span class="sxs-lookup"><span data-stu-id="eda7c-132">Element</span></span>|<span data-ttu-id="eda7c-133">Wenn Sie Folgendes verwenden...</span><span class="sxs-lookup"><span data-stu-id="eda7c-133">If you're using...</span></span>|<span data-ttu-id="eda7c-134">Für Kunden üblich?</span><span class="sxs-lookup"><span data-stu-id="eda7c-134">Common for customers?</span></span>|<span data-ttu-id="eda7c-135">Fügen Sie Folgendes hinzu ...</span><span class="sxs-lookup"><span data-stu-id="eda7c-135">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="eda7c-136">1</span><span class="sxs-lookup"><span data-stu-id="eda7c-136">1</span></span>|<span data-ttu-id="eda7c-137">Beliebiges E-Mail-System (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="eda7c-137">Any email system (required)</span></span>|<span data-ttu-id="eda7c-p108">Standard. Alle SPF TXT-Einträge beginnen mit dem folgenden Wert</span><span class="sxs-lookup"><span data-stu-id="eda7c-p108">Common. All SPF TXT records start with this value</span></span>|`v=spf1`|
   |<span data-ttu-id="eda7c-140">2</span><span class="sxs-lookup"><span data-stu-id="eda7c-140">2</span></span>|<span data-ttu-id="eda7c-141">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="eda7c-141">Exchange Online</span></span>|<span data-ttu-id="eda7c-142">Standard</span><span class="sxs-lookup"><span data-stu-id="eda7c-142">Common</span></span>|`include:spf.protection.outlook.com`|
   |<span data-ttu-id="eda7c-143">3</span><span class="sxs-lookup"><span data-stu-id="eda7c-143">3</span></span>|<span data-ttu-id="eda7c-144">Nur dediziert für Exchange Online</span><span class="sxs-lookup"><span data-stu-id="eda7c-144">Exchange Online dedicated only</span></span>|<span data-ttu-id="eda7c-145">Kein Standard</span><span class="sxs-lookup"><span data-stu-id="eda7c-145">Not common</span></span>|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |<span data-ttu-id="eda7c-146">4</span><span class="sxs-lookup"><span data-stu-id="eda7c-146">4</span></span>|<span data-ttu-id="eda7c-147">Office 365 Deutschland, nur Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="eda7c-147">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="eda7c-148">Kein Standard</span><span class="sxs-lookup"><span data-stu-id="eda7c-148">Not common</span></span>|`include:spf.protection.outlook.de`|
   |<span data-ttu-id="eda7c-149">5</span><span class="sxs-lookup"><span data-stu-id="eda7c-149">5</span></span>|<span data-ttu-id="eda7c-150">Drittanbieter-E-Mail-System</span><span class="sxs-lookup"><span data-stu-id="eda7c-150">Third-party email system</span></span>|<span data-ttu-id="eda7c-151">Kein Standard</span><span class="sxs-lookup"><span data-stu-id="eda7c-151">Not common</span></span>|`include:<domain_name>` <p> <span data-ttu-id="eda7c-152">\<domain_name\> ist die Domäne des Drittanbieter-E-Mail-Systems.</span><span class="sxs-lookup"><span data-stu-id="eda7c-152">\<domain_name\> is the domain of the third-party email system.</span></span>|
   |<span data-ttu-id="eda7c-153">6</span><span class="sxs-lookup"><span data-stu-id="eda7c-153">6</span></span>|<span data-ttu-id="eda7c-p109">Lokales E-Mail-System. Beispielsweise Exchange Online Protection und ein anderes E-Mail-System</span><span class="sxs-lookup"><span data-stu-id="eda7c-p109">On-premises email system. For example, Exchange Online Protection plus another email system</span></span>|<span data-ttu-id="eda7c-156">Kein Standard</span><span class="sxs-lookup"><span data-stu-id="eda7c-156">Not common</span></span>|<span data-ttu-id="eda7c-157">Verwenden Sie einen der folgenden Einträge für jedes zusätzliche E-Mail-System:</span><span class="sxs-lookup"><span data-stu-id="eda7c-157">Use one of these for each additional mail system:</span></span> <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> <span data-ttu-id="eda7c-158">\<IP_address\> und \<domain_name\> entsprechen jeweils der IP-Adresse und der Domäne des anderen E-Mail-Systems, das E-Mails im Auftrag Ihrer Domäne sendet.</span><span class="sxs-lookup"><span data-stu-id="eda7c-158">\<IP_address\> and \<domain_name\> are the IP address and domain of the other email system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="eda7c-159">7</span><span class="sxs-lookup"><span data-stu-id="eda7c-159">7</span></span>|<span data-ttu-id="eda7c-160">Beliebiges E-Mail-System (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="eda7c-160">Any email system (required)</span></span>|<span data-ttu-id="eda7c-p110">Standard. Alle SPF TXT-Einträge enden mit diesem Wert</span><span class="sxs-lookup"><span data-stu-id="eda7c-p110">Common. All SPF TXT records end with this value</span></span>|`<enforcement rule>` <p> <span data-ttu-id="eda7c-163">Kann einer von mehreren Werten sein.</span><span class="sxs-lookup"><span data-stu-id="eda7c-163">This can be one of several values.</span></span> <span data-ttu-id="eda7c-164">Empfohlen wird der Wert `-all`.</span><span class="sxs-lookup"><span data-stu-id="eda7c-164">We recommend the value `-all`.</span></span>|
   |

2. <span data-ttu-id="eda7c-165">Erstellen Sie Ihren SPF TXT-Eintrag, falls noch nicht geschehen, indem Sie die Syntax aus der Tabelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="eda7c-165">If you haven't already done so, form your SPF TXT record by using the syntax from the table.</span></span>

   <span data-ttu-id="eda7c-166">Wenn Sie beispielsweise vollständig in Office 365 gehostet werden (wenn Sie also keine lokalen E-Mail-Server haben), würde Ihr SPF TXT-Eintrag die Zeilen 1, 2 und 7 enthalten und wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="eda7c-166">For example, if you are hosted entirely in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   <span data-ttu-id="eda7c-167">**Das obige Beispiel ist der häufigste SPF TXT-Eintrag**.</span><span class="sxs-lookup"><span data-stu-id="eda7c-167">**The example above is the most common SPF TXT record**.</span></span> <span data-ttu-id="eda7c-168">Dieser Eintrag eignet sich für fast alle Benutzer, unabhängig davon, ob sich Ihr Microsoft-Rechenzentrum in den USA, in Europa (einschließlich Deutschland) oder an einem anderen Standort befindet.</span><span class="sxs-lookup"><span data-stu-id="eda7c-168">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="eda7c-p113">Wenn Sie jedoch Office 365 Deutschland, Teil von Microsoft Cloud Deutschland, gekauft haben, sollten Sie die „Include“-Anweisung aus Zeile 4 anstelle von Zeile 2 verwenden. Wenn Sie beispielsweise vollständig in Office 365 Deutschland gehostet werden (wenn Sie also keine lokalen E-Mail-Server haben), würde Ihr SPF TXT-Eintrag die Zeilen 1, 4 und 7 enthalten und wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="eda7c-p113">However, if you bought Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2. For example, if you are hosted entirely in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   <span data-ttu-id="eda7c-171">Wenn Sie bereits in Office 365 bereitgestellt und Ihre SPF TXT-Einträge für Ihre benutzerdefinierte Domäne eingerichtet haben und anschließend zu Office 365 Deutschland migrieren möchten, müssen Sie Ihren SPF TXT-Eintrag aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="eda7c-171">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="eda7c-172">Ändern Sie dazu `include:spf.protection.outlook.com` in `include:spf.protection.outlook.de`.</span><span class="sxs-lookup"><span data-stu-id="eda7c-172">To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.</span></span>

3. <span data-ttu-id="eda7c-173">Nachdem Sie Ihren SPF TXT-Eintrag erstellt haben, müssen Sie den Eintrag in DNS aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="eda7c-173">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="eda7c-174">**Sie dürfen nur einen SPF TXT-Eintrag pro Domäne haben.**</span><span class="sxs-lookup"><span data-stu-id="eda7c-174">**You can only have one SPF TXT record for a domain.**</span></span> <span data-ttu-id="eda7c-175">Wenn ein SPF TXT-Eintrag vorhanden ist, müssen Sie den vorhandenen Eintrag aktualisieren, statt einen neuen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="eda7c-175">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="eda7c-176">Wechseln Sie zu [Erstellen von DNS-Einträgen für Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), und wählen Sie dann den Link für Ihren DNS-Hostinganbieter aus.</span><span class="sxs-lookup"><span data-stu-id="eda7c-176">Go to [Create DNS records for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), and then select the link for your DNS host.</span></span>

4. <span data-ttu-id="eda7c-177">Testen Sie Ihren SPF TXT-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="eda7c-177">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="eda7c-178">Wie kann ich Subdomänen behandeln?</span><span class="sxs-lookup"><span data-stu-id="eda7c-178">How to handle subdomains?</span></span>

<span data-ttu-id="eda7c-179">Es ist wichtig zu beachten, *dass Sie für jede Subdomäne einen separaten Eintrag erstellen müssen, da Subdomänen nicht den SPF-Eintrag der Domäne der obersten Ebene erben*.</span><span class="sxs-lookup"><span data-stu-id="eda7c-179">It's important to note that *you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top-level domain*.</span></span>

<span data-ttu-id="eda7c-180">Ein Platzhalter-SPF-Eintrag (`*.`) ist für jede Domäne und Subdomäne erforderlich, um Angreifer daran zu hindern, E-Mails zu versenden, die vorgeben, von nicht existierenden Subdomänen zu stammen.</span><span class="sxs-lookup"><span data-stu-id="eda7c-180">A wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="eda7c-181">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="eda7c-181">For example:</span></span>

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a><span data-ttu-id="eda7c-182">Problembehandlung von SPF</span><span class="sxs-lookup"><span data-stu-id="eda7c-182">Troubleshooting SPF</span></span>

<span data-ttu-id="eda7c-p117">Gibt es Probleme mit Ihrem SPF TXT-Eintrag? Lesen Sie [Problembehandlung: Bewährte Methoden für SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span><span class="sxs-lookup"><span data-stu-id="eda7c-p117">Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>


## <a name="what-does-spf-email-authentication-actually-do"></a><span data-ttu-id="eda7c-185">Was ist der Zweck der SPF-E-Mail-Authentifizierung?</span><span class="sxs-lookup"><span data-stu-id="eda7c-185">What does SPF email authentication actually do?</span></span>

<span data-ttu-id="eda7c-p118">SPF identifiziert, welche E-Mail-Server zum Senden von E-Mails in Ihrem Auftrag berechtigt sind. Im Grunde trägt SPF zusammen mit DKIM, DMARC und anderen Technologien von Office 365 dazu bei, Spoofing und Phishing zu verhindern. SPF wird als TXT-Eintrag hinzugefügt, der von DNS verwendet wird, um zu identifizieren, welche E-Mail-Server E-Mails im Auftrag Ihrer benutzerdefinierten Domäne senden können. Empfänger-E-Mail-Systeme können auf den SPF TXT-Eintrag zugreifen, um festzustellen, ob eine Nachricht von Ihrer benutzerdefinierten Domäne über einen autorisierten Messagingserver kommt.</span><span class="sxs-lookup"><span data-stu-id="eda7c-p118">SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="eda7c-p119">Nehmen wir beispielsweise an, dass Ihre benutzerdefinierte Domäne „contoso.com“ Office 365 verwendet. Sie fügen einen SPF TXT-Eintrag hinzu, der die Office 365-Messagingserver als berechtigte E-Mail-Server für Ihre Domäne auflistet. Wenn der empfangende Messagingserver eine Nachricht von „joe@contoso.com“ erhält, sucht der Server im SPF TXT-Eintrag nach „contoso.com“ und findet heraus, ob die Nachricht gültig ist. Wenn der empfangende Server herausfindet, dass die Nachricht von einem anderen Server als den Office 365-Messagingservern kommt, die im SPF-Eintrag aufgelistet sind, kann der empfangende E-Mail-Server die Nachricht als Spam ablehnen.</span><span class="sxs-lookup"><span data-stu-id="eda7c-p119">For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="eda7c-p120">Wenn Ihre benutzerdefinierte Domäne keinen SPF TXT-Eintrag aufweist, können einige empfangende Server die Nachricht auch sofort ablehnen. Das liegt daran, dass der empfangende Server nicht überprüfen kann, ob die Nachricht von einem autorisierten Messagingserver stammt.</span><span class="sxs-lookup"><span data-stu-id="eda7c-p120">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="eda7c-p121">Wenn Sie bereits E-Mail für Office 365 eingerichtet haben, haben Sie bereits die Messagingserver von Microsoft in DNS als SPF TXT-Eintrag hinzugefügt. Es gibt jedoch einige Fälle, in denen Sie Ihren SPF TXT-Eintrag in DNS möglicherweise aktualisieren müssen. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="eda7c-p121">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:</span></span>

- <span data-ttu-id="eda7c-p122">In früheren Versionen mussten Sie Ihrer benutzerdefinierten Domäne einen anderen SPF TXT-Eintrag hinzufügen, wenn Sie SharePoint Online verwendet haben. Dies ist nicht mehr erforderlich. Diese Änderung sollte das Risiko reduzieren, dass SharePoint Online-Benachrichtigungsnachrichten im Junk-E-Mail-Ordner landen. Aktualisieren Sie Ihren SPF TXT-Eintrag, wenn Sie die Beschränkung von 10 Lookups erreichen und Fehlermeldungen erhalten wie z. B. „Suchlimit überschritten" und „Zu viele Hops".</span><span class="sxs-lookup"><span data-stu-id="eda7c-p122">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="eda7c-203">Wenn Sie eine Hybridumgebung mit Office 365 und Exchange (lokal) haben.</span><span class="sxs-lookup"><span data-stu-id="eda7c-203">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="eda7c-204">Sie möchten DKIM und DMARC einrichten (empfohlen).</span><span class="sxs-lookup"><span data-stu-id="eda7c-204">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="more-information-about-spf"></a><span data-ttu-id="eda7c-205">Weitere Informationen zu SPF</span><span class="sxs-lookup"><span data-stu-id="eda7c-205">More information about SPF</span></span>

<span data-ttu-id="eda7c-206">Erweiterte Beispiele, eine ausführlichere Erläuterung zur unterstützten SPF-Syntax, zu Spoofing, zur Problembehandlung und zur Unterstützung von SPF durch Office 365 finden Sie unter [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span><span class="sxs-lookup"><span data-stu-id="eda7c-206">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="next-steps-dkim-and-dmarc"></a><span data-ttu-id="eda7c-207">Nächste Schritte: DKIM und DMARC</span><span class="sxs-lookup"><span data-stu-id="eda7c-207">Next Steps: DKIM and DMARC</span></span>

 <span data-ttu-id="eda7c-208">SPF ist dafür vorgesehen, Spoofing möglichst zu verhindern, es gibt aber Spoofing-Techniken, vor denen SPF nicht schützen kann.</span><span class="sxs-lookup"><span data-stu-id="eda7c-208">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF can't protect against.</span></span> <span data-ttu-id="eda7c-209">Um sich dagegen zu verteidigen, sollten Sie nach dem Einrichten von SPF auch DKIM und DMARC für Office 365 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="eda7c-209">To defend against these, once you've set up SPF, you should configure DKIM and DMARC for Office 365.</span></span>

<span data-ttu-id="eda7c-210">Das Ziel der [DKIM](use-dkim-to-validate-outbound-email.md)-E-Mail-Authentifizierung ist es, nachzuweisen, dass der Inhalt der E-Mail nicht manipuliert wurde.</span><span class="sxs-lookup"><span data-stu-id="eda7c-210">[DKIM](use-dkim-to-validate-outbound-email.md) email authentication's goal is to prove the contents of the mail haven't been tampered with.</span></span>

<span data-ttu-id="eda7c-211">Das Ziel der [DMARC](use-dmarc-to-validate-email.md)-E-Mail-Authentifizierung ist es, sicherzustellen, dass die SPF- und DKIM-Informationen mit der Absenderadresse übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="eda7c-211">[DMARC](use-dmarc-to-validate-email.md) email authentication's goal is to make sure that SPF and DKIM information matches the From address.</span></span>

 <span data-ttu-id="eda7c-212">Erweiterte Beispiele und eine ausführlichere Erläuterung zur unterstützten SPF-Syntax finden Sie unter [Funktionsweise von SPF zur Verhinderung von Spoofing und Phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span><span class="sxs-lookup"><span data-stu-id="eda7c-212">For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="eda7c-213">*Wählen Sie unter „Feedback“ die Option „Diese Seite“ aus, wenn Sie Feedback zu dieser Dokumentation haben.*</span><span class="sxs-lookup"><span data-stu-id="eda7c-213">*Select 'This page' under 'Feedback' if you have feedback on this documentation.*</span></span>
