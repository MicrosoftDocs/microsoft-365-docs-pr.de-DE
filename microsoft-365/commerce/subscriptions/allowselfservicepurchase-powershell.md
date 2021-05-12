---
title: Verwenden von AllowSelfServicePurchase für das MS Commerce PowerShell-Modul
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
description: Erfahren Sie, wie Sie das AllowSelfServicePurchase PowerShell-Cmdlet verwenden, um den Self-Service-Kauf ein- oder auszuschalten.
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 03/18/2021
ms.openlocfilehash: 09161f69e72babe8270b339243d73444b93d9959
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333374"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="66b1e-103">Verwenden von AllowSelfServicePurchase für das MS Commerce PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="66b1e-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="66b1e-104">Das **MS Commerce** PowerShell-Modul ist jetzt im [PowerShell Gallery verfügbar.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="66b1e-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="66b1e-105">Das Modul enthält einen **PolicyID-Parameterwert** für **AllowSelfServicePurchase,** mit dem Sie steuern können, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können.</span><span class="sxs-lookup"><span data-stu-id="66b1e-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="66b1e-106">Sie können das **MS Commerce PowerShell-Modul** verwenden, um:</span><span class="sxs-lookup"><span data-stu-id="66b1e-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="66b1e-107">Anzeigen des Standardzustands des **Parameterwerts AllowSelfServicePurchase** – unabhängig davon, ob er aktiviert oder deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="66b1e-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="66b1e-108">Anzeigen einer Liste der zutreffenden Produkte und ob der Self-Service-Kauf aktiviert oder deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="66b1e-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="66b1e-109">Anzeigen oder Ändern der aktuellen Einstellung für ein bestimmtes Produkt, um sie entweder zu aktivieren oder zu deaktivieren</span><span class="sxs-lookup"><span data-stu-id="66b1e-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="66b1e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66b1e-110">Requirements</span></span>

<span data-ttu-id="66b1e-111">Für die Verwendung des **MS Commerce** PowerShell-Moduls benötigen Sie:</span><span class="sxs-lookup"><span data-stu-id="66b1e-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="66b1e-112">Ein Windows 10 Gerät</span><span class="sxs-lookup"><span data-stu-id="66b1e-112">A Windows 10 device</span></span>
- <span data-ttu-id="66b1e-113">Administratorberechtigung für das Gerät</span><span class="sxs-lookup"><span data-stu-id="66b1e-113">Administrator permission for the device</span></span>
- <span data-ttu-id="66b1e-114">Rolle "Globaler Administrator" oder "Abrechnungsadministrator" für Ihren Mandanten</span><span class="sxs-lookup"><span data-stu-id="66b1e-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="66b1e-115">Installieren des MS Commerce PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="66b1e-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="66b1e-116">Sie installieren das **MS Commerce** PowerShell-Modul einmal auf Ihrem Windows 10 und importieren es dann in jede gestartete PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="66b1e-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="66b1e-117">Laden Sie **das MS Commerce** PowerShell-Modul aus dem [PowerShell-Katalog herunter.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="66b1e-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="66b1e-118">Führen Sie den folgenden Befehl **aus,** um das MS Commerce PowerShell-Modul mit **PowerShellGet** zu installieren:</span><span class="sxs-lookup"><span data-stu-id="66b1e-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="66b1e-119">Importieren von MSCommerce in die PowerShell-Sitzung</span><span class="sxs-lookup"><span data-stu-id="66b1e-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="66b1e-120">Nachdem Sie das Modul auf Ihrem Windows 10 installiert haben, importieren Sie es in jede gestartete PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="66b1e-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="66b1e-121">Führen Sie den folgenden Befehl aus, um ihn in eine PowerShell-Sitzung zu importieren:</span><span class="sxs-lookup"><span data-stu-id="66b1e-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="66b1e-122">Verbinden mit Ihren Anmeldeinformationen zu MSCommerce</span><span class="sxs-lookup"><span data-stu-id="66b1e-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="66b1e-123">Führen Sie den folgenden Befehl aus, um eine Verbindung mit dem PowerShell-Modul mit Ihren Anmeldeinformationen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="66b1e-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="66b1e-124">Dieser Befehl verbindet die aktuelle PowerShell-Sitzung mit einem Azure Active Directory Mandanten.</span><span class="sxs-lookup"><span data-stu-id="66b1e-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="66b1e-125">Der Befehl fordert Sie auf, einen Benutzernamen und ein Kennwort für den Mandanten einzugeben, mit dem Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="66b1e-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="66b1e-126">Wenn die mehrstufige Authentifizierung für Ihre Anmeldeinformationen aktiviert ist, verwenden Sie die interaktive Option zum Anmelden.</span><span class="sxs-lookup"><span data-stu-id="66b1e-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="66b1e-127">Anzeigen von Details für AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="66b1e-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="66b1e-128">Führen Sie zum Anzeigen einer Beschreibung des **AllowSelfServicePurchase-Parameterwerts** und des Standardstatus basierend auf Ihrer Organisation den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="66b1e-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="66b1e-129">Anzeigen einer Liste der Self-Service-Einkaufsprodukte und deren Status</span><span class="sxs-lookup"><span data-stu-id="66b1e-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="66b1e-130">Führen Sie den folgenden Befehl aus, um eine Liste aller verfügbaren Self-Service-Einkaufsprodukte und den Status der einzelnen Produkte anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="66b1e-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="66b1e-131">In der folgenden Tabelle sind die verfügbaren Produkte und deren **ProductId aufgeführt.**</span><span class="sxs-lookup"><span data-stu-id="66b1e-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="66b1e-132">Produkt</span><span class="sxs-lookup"><span data-stu-id="66b1e-132">Product</span></span> | <span data-ttu-id="66b1e-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="66b1e-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="66b1e-134">Power Apps pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="66b1e-134">Power Apps per user</span></span> | <span data-ttu-id="66b1e-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="66b1e-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="66b1e-136">Power Automate pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="66b1e-136">Power Automate per user</span></span> | <span data-ttu-id="66b1e-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="66b1e-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="66b1e-138">Power Automate RPA</span><span class="sxs-lookup"><span data-stu-id="66b1e-138">Power Automate RPA</span></span> | <span data-ttu-id="66b1e-139">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="66b1e-139">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="66b1e-140">Power BI Premium (eigenständig)</span><span class="sxs-lookup"><span data-stu-id="66b1e-140">Power BI Premium (standalone)</span></span> | <span data-ttu-id="66b1e-141">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="66b1e-141">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="66b1e-142">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="66b1e-142">Power BI Pro</span></span> | <span data-ttu-id="66b1e-143">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="66b1e-143">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="66b1e-144">Project Plan 1</span><span class="sxs-lookup"><span data-stu-id="66b1e-144">Project Plan 1</span></span> | <span data-ttu-id="66b1e-145">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="66b1e-145">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="66b1e-146">Project Plan 3</span><span class="sxs-lookup"><span data-stu-id="66b1e-146">Project Plan 3</span></span> | <span data-ttu-id="66b1e-147">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="66b1e-147">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="66b1e-148">Visio Plan 1</span><span class="sxs-lookup"><span data-stu-id="66b1e-148">Visio Plan 1</span></span> | <span data-ttu-id="66b1e-149">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="66b1e-149">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="66b1e-150">Visio Plan 2</span><span class="sxs-lookup"><span data-stu-id="66b1e-150">Visio Plan 2</span></span> | <span data-ttu-id="66b1e-151">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="66b1e-151">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="66b1e-152">Anzeigen oder Festlegen des Status für AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="66b1e-152">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="66b1e-153">Nachdem Sie die Liste der Produkte angezeigt haben, die für den Self-Service-Kauf verfügbar sind, können Sie die Einstellung für ein bestimmtes Produkt anzeigen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="66b1e-153">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="66b1e-154">Führen Sie den folgenden Befehl aus, um die Richtlinieneinstellung für ein bestimmtes Produkt zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="66b1e-154">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="66b1e-155">Führen Sie den folgenden Befehl aus, um die Richtlinieneinstellung für ein bestimmtes Produkt zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="66b1e-155">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="66b1e-156">Führen Sie den folgenden Befehl aus, um die Richtlinieneinstellung für ein bestimmtes Produkt zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="66b1e-156">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="66b1e-157">Beispielskript zum Deaktivieren von AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="66b1e-157">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="66b1e-158">Im folgenden Beispiel erfahren Sie, wie Sie das **MS Commerce-Modul** importieren, sich mit Ihrem Konto anmelden, **die ProductId** für Power Automate erhalten und **dann AllowSelfServicePurchase** für dieses Produkt deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="66b1e-158">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="66b1e-159">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="66b1e-159">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="66b1e-160">Problem</span><span class="sxs-lookup"><span data-stu-id="66b1e-160">Problem</span></span>

<span data-ttu-id="66b1e-161">Die folgende Fehlermeldung wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="66b1e-161">You see the following error message:</span></span>

> <span data-ttu-id="66b1e-162">HandleError : Fehler beim Abrufen der Richtlinie mit PolicyId 'AllowSelfServicePurchase', ErrorMessage – Die zugrunde liegende Verbindung wurde geschlossen: Bei einem Senden ist ein unerwarteter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="66b1e-162">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="66b1e-163">Dies liegt möglicherweise an einer älteren Version von Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="66b1e-163">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="66b1e-164">Zum Verbinden dieses Diensts müssen Sie TLS 1.2 oder höher verwenden.</span><span class="sxs-lookup"><span data-stu-id="66b1e-164">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="66b1e-165">Lösung</span><span class="sxs-lookup"><span data-stu-id="66b1e-165">Solution</span></span>

<span data-ttu-id="66b1e-166">Upgrade auf TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="66b1e-166">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
