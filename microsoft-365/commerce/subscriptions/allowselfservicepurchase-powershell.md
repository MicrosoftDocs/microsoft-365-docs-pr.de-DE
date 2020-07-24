---
title: Verwenden von AllowSelfServicePurchase für das MSCommerce-PowerShell-Modul
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Hier erfahren Sie, wie Sie das AllowSelfServicePurchase PowerShell-Cmdlet verwenden, um Self-Service-Käufe ein-oder auszuschalten.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b35b62a97f8dc269be5db232e163391a8ce50658
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391542"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="71700-103">Verwenden von AllowSelfServicePurchase für das MSCommerce-PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="71700-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="71700-104">Das **MSCommerce** PowerShell-Modul steht nun im [PowerShell-Katalog](https://aka.ms/allowselfservicepurchase-powershell-gallery)zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="71700-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="71700-105">Das Modul enthält einen Parameterwert für die **Richtlinien** - **AllowSelfServicePurchase** , mit dem Sie steuern können, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können.</span><span class="sxs-lookup"><span data-stu-id="71700-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="71700-106">Sie können das **MSCommerce** -PowerShell-Modul verwenden, um Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="71700-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="71700-107">Anzeigen des Standardstatus des **AllowSelfServicePurchase** -Parameterwerts – unabhängig davon, ob er aktiviert oder deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="71700-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="71700-108">Anzeigen einer Liste der anwendbaren Produkte und der Aktivierung oder Deaktivierung von Self-Service-Käufen</span><span class="sxs-lookup"><span data-stu-id="71700-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="71700-109">Anzeigen oder Ändern der aktuellen Einstellung für ein bestimmtes Produkt, um es entweder zu aktivieren oder zu deaktivieren</span><span class="sxs-lookup"><span data-stu-id="71700-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="71700-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71700-110">Requirements</span></span>

<span data-ttu-id="71700-111">Um das **MSCommerce** PowerShell-Modul verwenden zu können, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="71700-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="71700-112">Ein Windows 10-Gerät</span><span class="sxs-lookup"><span data-stu-id="71700-112">A Windows 10 device</span></span>
- <span data-ttu-id="71700-113">Administrator Berechtigung für das Gerät</span><span class="sxs-lookup"><span data-stu-id="71700-113">Administrator permission for the device</span></span>
- <span data-ttu-id="71700-114">Globale oder abrechnungsadministrator Rolle für Ihren Mandanten</span><span class="sxs-lookup"><span data-stu-id="71700-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="71700-115">Installieren des MSCommerce PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="71700-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="71700-116">Sie installieren das **MSCommerce** PowerShell-Modul auf Ihrem Windows 10-Gerät einmal und importieren es dann in jede von Ihnen gestartete PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="71700-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="71700-117">Laden Sie das **MSCommerce** PowerShell-Modul aus dem [PowerShell-Katalog](https://aka.ms/allowselfservicepurchase-powershell-gallery)herunter.</span><span class="sxs-lookup"><span data-stu-id="71700-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="71700-118">Führen Sie den folgenden Befehl aus, um das **MSCommerce** PowerShell-Modul mit **PowerShellGet**zu installieren:</span><span class="sxs-lookup"><span data-stu-id="71700-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="71700-119">Importieren von MSCommerce in die PowerShell-Sitzung</span><span class="sxs-lookup"><span data-stu-id="71700-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="71700-120">Nachdem Sie das Modul auf Ihrem Windows 10-Gerät installiert haben, importieren Sie es in jede PowerShell-Sitzung, die Sie starten.</span><span class="sxs-lookup"><span data-stu-id="71700-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="71700-121">Führen Sie den folgenden Befehl aus, um ihn in eine PowerShell-Sitzung zu importieren:</span><span class="sxs-lookup"><span data-stu-id="71700-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="71700-122">Herstellen einer Verbindung mit MSCommerce mit Ihren Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="71700-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="71700-123">Führen Sie den folgenden Befehl aus, um eine Verbindung mit dem PowerShell-Modul mit Ihren Anmeldeinformationen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="71700-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="71700-124">Mit diesem Befehl wird die aktuelle PowerShell-Sitzung mit einem Azure-Active Directory-Mandanten verbunden.</span><span class="sxs-lookup"><span data-stu-id="71700-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="71700-125">Mit dem Befehl werden Sie aufgefordert, einen Benutzernamen und ein Kennwort für den Mandanten einzugeben, mit dem Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="71700-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="71700-126">Wenn die mehrstufige Authentifizierung für Ihre Anmeldeinformationen aktiviert ist, verwenden Sie die interaktive Option, um sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="71700-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="71700-127">Anzeigen von Details für AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="71700-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="71700-128">Führen Sie den folgenden Befehl aus, um eine Beschreibung des **AllowSelfServicePurchase** -Parameterwerts und des Standardstatus basierend auf Ihrer Organisation anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="71700-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="71700-129">Anzeigen einer Liste von Self-Service-Kauf Produkten und deren Status</span><span class="sxs-lookup"><span data-stu-id="71700-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="71700-130">Führen Sie den folgenden Befehl aus, um eine Liste aller verfügbaren Self-Service-Einkaufsprodukte und den jeweiligen Status anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="71700-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="71700-131">In der folgenden Tabelle sind die verfügbaren Produkte und deren **ProductID**aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="71700-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="71700-132">Produkt</span><span class="sxs-lookup"><span data-stu-id="71700-132">Product</span></span> | <span data-ttu-id="71700-133">ProductID</span><span class="sxs-lookup"><span data-stu-id="71700-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="71700-134">Power-apps pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="71700-134">Power Apps per user</span></span> | <span data-ttu-id="71700-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="71700-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="71700-136">Power-Automatisierung pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="71700-136">Power Automate per user</span></span> | <span data-ttu-id="71700-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="71700-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="71700-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="71700-138">Power BI Pro</span></span> | <span data-ttu-id="71700-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="71700-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="71700-140">Anzeigen oder Festlegen des Status für AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="71700-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="71700-141">Nachdem Sie die Liste der Produkte angezeigt haben, die für Self-Service-Einkauf verfügbar sind, können Sie die Einstellung für ein bestimmtes Produkt anzeigen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="71700-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="71700-142">Um die Richtlinieneinstellung für ein bestimmtes Produkt abzurufen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="71700-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="71700-143">Führen Sie den folgenden Befehl aus, um die Richtlinieneinstellung für ein bestimmtes Produkt zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="71700-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="71700-144">Führen Sie den folgenden Befehl aus, um die Richtlinieneinstellung für ein bestimmtes Produkt zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="71700-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="71700-145">Beispielskript zum Deaktivieren von AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="71700-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="71700-146">Im folgenden Beispiel wird erläutert, wie Sie das **MSCommerce** -Modul importieren, sich mit Ihrem Konto anmelden, die **ProductID** für Power automatisieren und dann **AllowSelfServicePurchase** für dieses Produkt deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="71700-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="71700-147">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="71700-147">Troubleshooting</span></span>

<span data-ttu-id="71700-148">**Problem**</span><span class="sxs-lookup"><span data-stu-id="71700-148">**Problem**</span></span>

<span data-ttu-id="71700-149">Die folgende Fehlermeldung wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="71700-149">You see the following error message:</span></span>

> <span data-ttu-id="71700-150">HandleError: Fehler beim Abrufen einer Richtlinie mit der Richtlinien-Nr "AllowSelfServicePurchase", ErrorMessage – die zugrunde liegende Verbindung wurde geschlossen: ein unerwarteter Fehler ist bei einem senden aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="71700-150">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="71700-151">Dies kann an einer älteren Version von Transport Layer Security (TLS) liegen.</span><span class="sxs-lookup"><span data-stu-id="71700-151">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="71700-152">Um diesen Dienst zu verbinden, müssen Sie TLS 1,2 oder höher verwenden.</span><span class="sxs-lookup"><span data-stu-id="71700-152">To connect this service you need to use TLS 1.2 or greater</span></span>

<span data-ttu-id="71700-153">**Lösung**</span><span class="sxs-lookup"><span data-stu-id="71700-153">**Solution**</span></span>

<span data-ttu-id="71700-154">Upgrade auf TLS 1,2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="71700-154">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
