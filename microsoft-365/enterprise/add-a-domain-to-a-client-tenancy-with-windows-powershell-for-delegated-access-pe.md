---
title: Hinzufügen einer Domäne zu einem Clientmandanten mit Windows PowerShell für DAP-Partner
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: 'Zusammenfassung: Verwenden Sie PowerShell für Microsoft 365, um einem vorhandenen Kundenmandanten einen alternativen Domänennamen hinzuzufügen.'
ms.openlocfilehash: 5ebbe11da9a93669945e7e3b096ce7afa18b5d3a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288431"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a><span data-ttu-id="62ac3-103">Hinzufügen einer Domäne zu einem Kundenmandanten mit Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)</span><span class="sxs-lookup"><span data-stu-id="62ac3-103">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>

<span data-ttu-id="62ac3-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="62ac3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="62ac3-105">Sie können mit PowerShell neue Domänen erstellen und dem Mandanten Ihres Kunden zuordnen, um Microsoft 365 schneller als die verwendung der Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="62ac3-105">You can create and associate new domains with your customer's tenancy with PowerShell for Microsoft 365 faster than using the Microsoft 365 admin center.</span></span>

<span data-ttu-id="62ac3-106">DAP-Partner (Delegated Access Permission, delegierte Zugriffsberechtigung) sind Syndication-Partner und Cloudlösungsanbieter (Cloud Solution Providers, CSP).</span><span class="sxs-lookup"><span data-stu-id="62ac3-106">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="62ac3-107">Häufig handelt es sich um Netzwerk- oder Telekom-Anbieter für andere Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-107">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="62ac3-108">Sie bündeln Microsoft 365 Abonnements in ihren Serviceangeboten für ihre Kunden.</span><span class="sxs-lookup"><span data-stu-id="62ac3-108">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="62ac3-109">Wenn sie ein Microsoft 365 Abonnement verkaufen, wird ihnen automatisch die Berechtigung "Verwalten im Auftrag von" (Administer On Behalf Of, AOBO) für die Kundenmandanten gewährt, damit sie die Kundenmandanten verwalten und darüber berichten können.</span><span class="sxs-lookup"><span data-stu-id="62ac3-109">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="62ac3-110">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="62ac3-110">What do you need to know before you begin?</span></span>

<span data-ttu-id="62ac3-111">Für die Verfahren in diesem Thema müssen Sie eine Verbindung mit [Verbinden mit Microsoft 365 mit PowerShell](connect-to-microsoft-365-powershell.md)herstellen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-111">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="62ac3-112">Sie benötigen auch die Administratoranmeldeinformationen Ihres Partnermandanten.</span><span class="sxs-lookup"><span data-stu-id="62ac3-112">You also need your partner tenant administrator credentials.</span></span>

<span data-ttu-id="62ac3-113">Sie benötigen außerdem die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="62ac3-113">You also need the following information:</span></span>

- <span data-ttu-id="62ac3-114">Sie benötigen den vollqualifizierten Domänennamen (FQDN), den der Kunde verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="62ac3-114">You need the fully qualified domain name (FQDN) that your customer wants.</span></span>

- <span data-ttu-id="62ac3-115">Sie benötigen die **TenantId** des Kunden.</span><span class="sxs-lookup"><span data-stu-id="62ac3-115">You need the customer's **TenantId**.</span></span>

- <span data-ttu-id="62ac3-p102">Der FQDN muss bei einer Registrierungsstelle für Internetdomänennamen, wie z. B. GoDaddy, registriert sein. Weitere Informationen für die öffentliche Registrierung eines Domänennamens finden Sie unter [Erwerben eines Domänennamens](../admin/get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="62ac3-p102">The FQDN must be registered with an Internet domain name service (DNS) registrar, such as GoDaddy. For more information on how to publically register a domain name, see [How to buy a domain name](../admin/get-help-with-domains/buy-a-domain-name.md).</span></span>

- <span data-ttu-id="62ac3-118">Sie müssen wissen, wie Sie einen TXT-Eintrag zur registrierten DNS-Zone für die DNS-Registrierungsstelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-118">You need to know how to add a TXT record to the registered DNS zone for your DNS registrar.</span></span> <span data-ttu-id="62ac3-119">Weitere Informationen zum Hinzufügen eines TXT-Eintrags finden Sie unter [Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="62ac3-119">For more information on how to add a TXT record, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="62ac3-120">Wenn Sie diese Verfahren nicht durchführen können, müssen Sie die für die DNS-Registrierungsstelle anwendbaren Verfahren ermitteln.</span><span class="sxs-lookup"><span data-stu-id="62ac3-120">If those procedures don't work for you, you will need to find the procedures for your DNS registrar.</span></span>

## <a name="create-domains"></a><span data-ttu-id="62ac3-121">Erstellen von Domänen</span><span class="sxs-lookup"><span data-stu-id="62ac3-121">Create domains</span></span>

 <span data-ttu-id="62ac3-p104">Ihre Kunden werden Sie wahrscheinlich bitten, weitere Domänen für ihren Mandanten zu erstellen, da sie die Standarddomäne<Domäne>.onmicrosoft.comwahrscheinlich nicht als primären Domäne verwenden möchten, um ihr Unternehmen im Internet weltweit zu repräsentieren. Dieses Verfahren leitet Sie durch die Schritte zum Erstellen einer neuen Domäne, die Sie mit dem Kundenmandanten verknüpfen können.</span><span class="sxs-lookup"><span data-stu-id="62ac3-p104">Your customers will likely ask you to create additional domains to associate with their tenancy because they don't want the default <domain>.onmicrosoft.com domain to be the primary one that represents their corporate identities to the world. This procedure walks you through creating a new domain associated with your customer's tenancy.</span></span>

> [!NOTE]
> <span data-ttu-id="62ac3-124">Um einige dieser Vorgänge auszuführen, muss das Partneradministratorkonto, mit dem Sie sich anmelden, auf **"Vollständige Verwaltung"** für die **Zuweisung des administrativen Zugriffs auf Unternehmen** festgelegt werden, die Sie in den Details des Administratorkontos im Microsoft 365 Admin Center unterstützen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-124">To perform some of these operations, the partner administrator account you sign in with must be set to **Full administration** for the **Assign administrative access to companies you support** setting found in the details of the admin account in the Microsoft 365 admin center.</span></span> <span data-ttu-id="62ac3-125">Weitere Informationen zum Verwalten von Partneradministratorrollen finden Sie unter ["Partner: Anbieten delegierter Verwaltung".](https://go.microsoft.com/fwlink/p/?LinkId=532435)</span><span class="sxs-lookup"><span data-stu-id="62ac3-125">For more information on managing partner administrator roles, see [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span></span>

### <a name="create-the-domain-in-azure-active-directory"></a><span data-ttu-id="62ac3-126">Erstellen Sie die Domäne in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="62ac3-126">Create the domain in Azure Active Directory</span></span>

<span data-ttu-id="62ac3-127">Dieser Befehl erstellt die Domäne in Azure Active Directory, ordnet sie jedoch nicht der öffentlich registrierten Domäne zu.</span><span class="sxs-lookup"><span data-stu-id="62ac3-127">This command creates the domain in Azure Active Directory but does not associate it with the publicly registered domain.</span></span> <span data-ttu-id="62ac3-128">Dies kommt, wenn Sie nachweisen, dass Sie die öffentlich registrierte Domäne bei Microsoft Microsoft 365 für Unternehmen besitzen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-128">That comes when you prove that you own the publicly registered domain to Microsoft Microsoft 365 for enterprises.</span></span>

```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

> [!NOTE]
> <span data-ttu-id="62ac3-129">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-129">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="62ac3-130">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-130">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a><span data-ttu-id="62ac3-131">Abrufen der Daten für den DNS-TXT-Überprüfungseintrag</span><span class="sxs-lookup"><span data-stu-id="62ac3-131">Get the data for the DNS TXT verification record</span></span>

 <span data-ttu-id="62ac3-132">Microsoft 365 generiert die spezifischen Daten, die Sie in den DNS TXT-Überprüfungseintrag eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-132">Microsoft 365 will generate the specific data that you need to place into the DNS TXT verification record.</span></span> <span data-ttu-id="62ac3-133">Führen Sie diesen Befehl aus, um die Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-133">To get the data, run this command.</span></span>

```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

<span data-ttu-id="62ac3-134">Dadurch erhalten Sie die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62ac3-134">This will give you output like:</span></span>

 `Label: domainname.com`

 `Text: MS=ms########`

 `Ttl: 3600`

> [!NOTE]
> <span data-ttu-id="62ac3-135">Sie benötigen diesen Text, um den TXT-Eintrag in der öffentlich registrierten DNS-Zone zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-135">You will need this text to create the TXT record in the publicly registered DNS zone.</span></span> <span data-ttu-id="62ac3-136">Stellen Sie sicher, dass Sie ihn kopieren und speichern.</span><span class="sxs-lookup"><span data-stu-id="62ac3-136">Be sure to copy and save it.</span></span>

### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a><span data-ttu-id="62ac3-137">Hinzufügen eines TXT-Eintrags zur öffentlich registrierten DNS-Zone</span><span class="sxs-lookup"><span data-stu-id="62ac3-137">Add a TXT record to the publically registered DNS zone</span></span>

<span data-ttu-id="62ac3-138">Bevor Microsoft 365 beginnen, Datenverkehr zu akzeptieren, der an den öffentlich registrierten Domänennamen weitergeleitet wird, müssen Sie nachweisen, dass Sie der Besitzer der Domäne sind und über Administratorberechtigungen für die Domäne verfügen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-138">Before Microsoft 365 will start accepting traffic that is directed to the publicly registered domain name, you must prove that you own and have administrator permissions to the domain.</span></span> <span data-ttu-id="62ac3-139">Sie weisen nach, dass Sie die Domäne besitzen, indem Sie einen TXT-Eintrag in der Domäne erstellen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-139">You prove you own the domain by creating a TXT record in the domain.</span></span> <span data-ttu-id="62ac3-140">Ein TXT-Eintrag hat keine Auswirkungen auf die Domäne, und er kann gelöscht werden, nachdem die Besitzrechte an der Domäne nachgewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="62ac3-140">A TXT record doesn't do anything in your domain, and it can be deleted after your ownership of the domain is established.</span></span> <span data-ttu-id="62ac3-141">Um die TXT-Einträge zu erstellen, führen Sie die Verfahren unter [Hinzufügen von DNS-Einträgen aus, um Ihre Domäne zu verbinden.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="62ac3-141">To create the TXT records, follow the procedures at [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="62ac3-142">Wenn Sie diese Verfahren nicht durchführen können, müssen Sie die für die DNS-Registrierungsstelle anwendbaren Verfahren ermitteln.</span><span class="sxs-lookup"><span data-stu-id="62ac3-142">If those procedures don't work for you , you need to find the procedures for your DNS registrar.</span></span>

<span data-ttu-id="62ac3-p111">Bestätigen Sie die erfolgreiche Erstellung des TXT-Eintrags über Nslookup. Verwenden Sie die folgende Syntax.</span><span class="sxs-lookup"><span data-stu-id="62ac3-p111">Confirm the successful creation of the TXT record via nslookup. Follow this syntax.</span></span>

```console
nslookup -type=TXT <FQDN of registered domain>
```

<span data-ttu-id="62ac3-145">Dadurch erhalten Sie die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62ac3-145">This will give you output like:</span></span>

 `Non-authoritative answer:`

 `FQDN of the registered domain`

 `text=MS=ms########`

### <a name="validate-domain-ownership-in-microsoft-365"></a><span data-ttu-id="62ac3-146">Überprüfen des Domänenbesitzes in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62ac3-146">Validate domain ownership in Microsoft 365</span></span>

<span data-ttu-id="62ac3-147">In diesem letzten Schritt überprüfen Sie, Microsoft 365, dass Sie die öffentlich registrierte Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="62ac3-147">In this last step, you validate to Microsoft 365 that you own the publically registered domain.</span></span> <span data-ttu-id="62ac3-148">Nach diesem Schritt akzeptiert Microsoft 365 den Datenverkehr, der an den neuen Domänennamen weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="62ac3-148">After this step, Microsoft 365 will begin accepting traffic routed to the new domain name.</span></span> <span data-ttu-id="62ac3-149">Um das Erstellen und Registrieren der neuen Domäne abzuschließen, führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="62ac3-149">To complete the domain creation and registration process, run this command.</span></span>

```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="62ac3-150">Dieser Befehl gibt keine Ausgabe zurück. Um sicherzustellen, dass dies funktioniert hat, führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="62ac3-150">This command won't return any output, so to confirm that this worked, run this command.</span></span>

```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="62ac3-151">Dadurch wird in etwa Folgendes zurückgegeben</span><span class="sxs-lookup"><span data-stu-id="62ac3-151">This will return something like this</span></span>

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

## <a name="see-also"></a><span data-ttu-id="62ac3-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62ac3-152">See also</span></span>

[<span data-ttu-id="62ac3-153">Hilfe für Partner</span><span class="sxs-lookup"><span data-stu-id="62ac3-153">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)
