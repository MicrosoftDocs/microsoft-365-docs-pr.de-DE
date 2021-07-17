---
title: Verwenden von AllowSelfServicePurchase für das MSShell-PowerShell-Modul
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_ssp
search.appverid:
- MET150
description: Erfahren Sie, wie Sie das PowerShell-Cmdlet "AllowSelfServicePurchase" verwenden, um den Self-Service-Kauf zu aktivieren oder zu deaktivieren.
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 07/16/2021
ms.openlocfilehash: 77cb1c753db22929ea2c3d14226a3927e6406b89
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461363"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="0069e-103">Verwenden von AllowSelfServicePurchase für das MSShell-PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="0069e-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="0069e-104">Das **MSShell-PowerShell-Modul** ist jetzt im [PowerShell-Katalog](https://aka.ms/allowselfservicepurchase-powershell-gallery)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0069e-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="0069e-105">Das Modul enthält einen **PolicyID-Parameterwert** für **AllowSelfServicePurchase,** mit dem Sie steuern können, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können.</span><span class="sxs-lookup"><span data-stu-id="0069e-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="0069e-106">Sie können das **MSShell-PowerShell-Modul** für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="0069e-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="0069e-107">Anzeigen des Standardzustands des **AllowSelfServicePurchase-Parameterwerts** – unabhängig davon, ob er aktiviert oder deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="0069e-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="0069e-108">Anzeigen einer Liste der anwendbaren Produkte und ob self-service purchase aktiviert oder deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="0069e-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="0069e-109">Anzeigen oder Ändern der aktuellen Einstellung für ein bestimmtes Produkt, um es zu aktivieren oder zu deaktivieren</span><span class="sxs-lookup"><span data-stu-id="0069e-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="0069e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0069e-110">Requirements</span></span>

<span data-ttu-id="0069e-111">Zum Verwenden des **MSShell-PowerShell-Moduls** benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0069e-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="0069e-112">Ein Windows 10 Gerät</span><span class="sxs-lookup"><span data-stu-id="0069e-112">A Windows 10 device</span></span>
- <span data-ttu-id="0069e-113">PowerShell 5 oder darunter.</span><span class="sxs-lookup"><span data-stu-id="0069e-113">PowerShell 5 or below.</span></span> <span data-ttu-id="0069e-114">PowerShell 6.x/7.x wird derzeit mit diesem Modul nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0069e-114">Currently, PowerShell 6.x/7.x isn't supported with this module.</span></span>
- <span data-ttu-id="0069e-115">Administratorberechtigung für das Gerät</span><span class="sxs-lookup"><span data-stu-id="0069e-115">Administrator permission for the device</span></span>
- <span data-ttu-id="0069e-116">Rolle "Globaler Administrator" oder "Abrechnungsadministrator" für Ihren Mandanten</span><span class="sxs-lookup"><span data-stu-id="0069e-116">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="0069e-117">Installieren des MSShell-PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="0069e-117">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="0069e-118">Installieren Sie das **MSShell-PowerShell-Modul** einmal auf Ihrem Windows 10 Gerät, und importieren Sie es dann in jede PowerShell-Sitzung, die Sie starten.</span><span class="sxs-lookup"><span data-stu-id="0069e-118">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="0069e-119">Laden Sie das **MSShell-PowerShell-Modul** aus dem [PowerShell-Katalog herunter.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="0069e-119">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="0069e-120">Führen Sie den folgenden Befehl aus, um das **MSShell PowerShell-Modul** mit **PowerShellGet** zu installieren:</span><span class="sxs-lookup"><span data-stu-id="0069e-120">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="0069e-121">Importieren von MSImport in die PowerShell-Sitzung</span><span class="sxs-lookup"><span data-stu-id="0069e-121">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="0069e-122">Nachdem Sie das Modul auf Ihrem Windows 10 Gerät installiert haben, importieren Sie es in jede PowerShell-Sitzung, die Sie starten.</span><span class="sxs-lookup"><span data-stu-id="0069e-122">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="0069e-123">Führen Sie den folgenden Befehl aus, um sie in eine PowerShell-Sitzung zu importieren:</span><span class="sxs-lookup"><span data-stu-id="0069e-123">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="0069e-124">Verbinden mit Ihren Anmeldeinformationen zu MS Commerce</span><span class="sxs-lookup"><span data-stu-id="0069e-124">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="0069e-125">Führen Sie den folgenden Befehl aus, um eine Verbindung mit dem PowerShell-Modul mit Ihren Anmeldeinformationen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0069e-125">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="0069e-126">Mit diesem Befehl wird die aktuelle PowerShell-Sitzung mit einem Azure Active Directory Mandanten verbunden.</span><span class="sxs-lookup"><span data-stu-id="0069e-126">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="0069e-127">Der Befehl fordert Sie auf, einen Benutzernamen und ein Kennwort für den Mandanten einzugeben, mit dem Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0069e-127">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="0069e-128">Wenn die mehrstufige Authentifizierung für Ihre Anmeldeinformationen aktiviert ist, verwenden Sie die interaktive Option zum Anmelden.</span><span class="sxs-lookup"><span data-stu-id="0069e-128">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="0069e-129">Anzeigen von Details für AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="0069e-129">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="0069e-130">Führen Sie den folgenden Befehl aus, um eine Beschreibung des **AllowSelfServicePurchase-Parameterwerts** und des Standardstatus basierend auf Ihrer Organisation anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="0069e-130">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="0069e-131">Anzeigen einer Liste von Self-Service-Einkaufsprodukten und deren Status</span><span class="sxs-lookup"><span data-stu-id="0069e-131">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="0069e-132">Führen Sie den folgenden Befehl aus, um eine Liste aller verfügbaren Self-Service Purchase-Produkte und den Status der einzelnen Produkte anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="0069e-132">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="0069e-133">In der folgenden Tabelle sind die verfügbaren Produkte und ihre **ProductId aufgeführt.**</span><span class="sxs-lookup"><span data-stu-id="0069e-133">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="0069e-134">Produkt</span><span class="sxs-lookup"><span data-stu-id="0069e-134">Product</span></span> | <span data-ttu-id="0069e-135">Productid</span><span class="sxs-lookup"><span data-stu-id="0069e-135">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="0069e-136">Power Apps pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="0069e-136">Power Apps per user</span></span> | <span data-ttu-id="0069e-137">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="0069e-137">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="0069e-138">Power Automate pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="0069e-138">Power Automate per user</span></span> | <span data-ttu-id="0069e-139">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="0069e-139">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="0069e-140">Power Automate Rpa</span><span class="sxs-lookup"><span data-stu-id="0069e-140">Power Automate RPA</span></span> | <span data-ttu-id="0069e-141">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="0069e-141">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="0069e-142">Power BI Premium (eigenständig)</span><span class="sxs-lookup"><span data-stu-id="0069e-142">Power BI Premium (standalone)</span></span> | <span data-ttu-id="0069e-143">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="0069e-143">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="0069e-144">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="0069e-144">Power BI Pro</span></span> | <span data-ttu-id="0069e-145">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="0069e-145">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="0069e-146">Project Plan 1</span><span class="sxs-lookup"><span data-stu-id="0069e-146">Project Plan 1</span></span> | <span data-ttu-id="0069e-147">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="0069e-147">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="0069e-148">Project Plan 3</span><span class="sxs-lookup"><span data-stu-id="0069e-148">Project Plan 3</span></span> | <span data-ttu-id="0069e-149">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="0069e-149">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="0069e-150">Visio Plan 1</span><span class="sxs-lookup"><span data-stu-id="0069e-150">Visio Plan 1</span></span> | <span data-ttu-id="0069e-151">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="0069e-151">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="0069e-152">Visio Plan 2</span><span class="sxs-lookup"><span data-stu-id="0069e-152">Visio Plan 2</span></span> | <span data-ttu-id="0069e-153">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="0069e-153">CFQ7TTC0KXN8</span></span> |
| <span data-ttu-id="0069e-154">Windows 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0069e-154">Windows 365 Enterprise</span></span> | <span data-ttu-id="0069e-155">CFQ7TTC0HHS9</span><span class="sxs-lookup"><span data-stu-id="0069e-155">CFQ7TTC0HHS9</span></span> |
| <span data-ttu-id="0069e-156">Windows 365 Business</span><span class="sxs-lookup"><span data-stu-id="0069e-156">Windows 365 Business</span></span> | <span data-ttu-id="0069e-157">CFQ7TTC0J203</span><span class="sxs-lookup"><span data-stu-id="0069e-157">CFQ7TTC0J203</span></span> |
| <span data-ttu-id="0069e-158">Windows 365 Business mit Windows Hybridvorteil</span><span class="sxs-lookup"><span data-stu-id="0069e-158">Windows 365 Business with Windows Hybrid Benefit</span></span> | <span data-ttu-id="0069e-159">CFQ7TTC0HX99</span><span class="sxs-lookup"><span data-stu-id="0069e-159">CFQ7TTC0HX99</span></span> |
## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="0069e-160">Anzeigen oder Festlegen des Status für AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="0069e-160">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="0069e-161">Nachdem Sie die Liste der für den Self-Service-Kauf verfügbaren Produkte angezeigt haben, können Sie die Einstellung für ein bestimmtes Produkt anzeigen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="0069e-161">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="0069e-162">Führen Sie den folgenden Befehl aus, um die Richtlinieneinstellung für ein bestimmtes Produkt abzurufen:</span><span class="sxs-lookup"><span data-stu-id="0069e-162">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="0069e-163">Führen Sie den folgenden Befehl aus, um die Richtlinieneinstellung für ein bestimmtes Produkt zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="0069e-163">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="0069e-164">Führen Sie den folgenden Befehl aus, um die Richtlinieneinstellung für ein bestimmtes Produkt zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="0069e-164">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="0069e-165">Beispielskript zum Deaktivieren von AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="0069e-165">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="0069e-166">Das folgende Beispiel führt Sie durch das Importieren des **MSBuild-Moduls,** das Anmelden mit Ihrem Konto, das Abrufen der **ProductId** für Power Automate und das Deaktivieren von **AllowSelfServicePurchase** für dieses Produkt.</span><span class="sxs-lookup"><span data-stu-id="0069e-166">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="0069e-167">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="0069e-167">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="0069e-168">Problem</span><span class="sxs-lookup"><span data-stu-id="0069e-168">Problem</span></span>

<span data-ttu-id="0069e-169">Die folgende Fehlermeldung wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0069e-169">You see the following error message:</span></span>

> <span data-ttu-id="0069e-170">HandleError: Fehler beim Abrufen der Richtlinie mit "AllowSelfServicePurchase", ErrorMessage : Die zugrunde liegende Verbindung wurde geschlossen: Beim Senden ist ein unerwarteter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0069e-170">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="0069e-171">Dies kann auf eine ältere Version von Transport Layer Security (TLS) zurückzuführen sein.</span><span class="sxs-lookup"><span data-stu-id="0069e-171">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="0069e-172">Um diesen Dienst zu verbinden, müssen Sie TLS 1.2 oder höher verwenden.</span><span class="sxs-lookup"><span data-stu-id="0069e-172">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="0069e-173">Lösung</span><span class="sxs-lookup"><span data-stu-id="0069e-173">Solution</span></span>

<span data-ttu-id="0069e-174">Upgrade auf TLS 1.2: (/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="0069e-174">Upgrade to TLS 1.2: (/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a><span data-ttu-id="0069e-175">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="0069e-175">Related content</span></span>

<span data-ttu-id="0069e-176">[Verwalten von Self-Service-Käufen (Administrator)](manage-self-service-purchases-admins.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="0069e-176">[Manage self-service purchases (Admin)](manage-self-service-purchases-admins.md) (article)</span></span>

<span data-ttu-id="0069e-177">[Faq zum Self-Service-Kauf](self-service-purchase-faq.yml) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="0069e-177">[Self-service purchase FAQ](self-service-purchase-faq.yml) (article)</span></span>
