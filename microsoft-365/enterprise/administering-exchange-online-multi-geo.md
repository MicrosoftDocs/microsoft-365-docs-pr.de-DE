---
title: Verwalten von Exchange Online-Postfächern in einer Multi-Geo-Umgebung
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Hier erfahren Sie, wie Sie Exchange Online Multi-Geo-Einstellungen in Ihrer Microsoft 365-Umgebung mit PowerShell verwalten.
ms.openlocfilehash: ea7090cd65634138f9677960beab7770825a6e86
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950676"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="38ac7-103">Verwalten von Exchange Online-Postfächern in einer Multi-Geo-Umgebung</span><span class="sxs-lookup"><span data-stu-id="38ac7-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="38ac7-104">Exchange Online PowerShell ist erforderlich, um Multi-Geo-Eigenschaften in Ihrer Microsoft 365-Umgebung anzuzeigen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="38ac7-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="38ac7-105">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="38ac7-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="38ac7-106">Sie benötigen das [Microsoft Azure Active Directory PowerShell-Modul](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 oder später in v1.x, um die **PreferredDataLocation**-Eigenschaft an Benutzerobjekten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="38ac7-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="38ac7-107">Benutzerobjekte, die über AAD Connect mit AAD synchronisiert werden, können ihren **PreferredDataLocation**-Wert direkt über AAD PowerShell ändern lassen.</span><span class="sxs-lookup"><span data-stu-id="38ac7-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="38ac7-108">Nur-Cloud-Benutzerobjekte können über AAD PowerShell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="38ac7-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="38ac7-109">Wie Sie eine Verbindung mit Azure AD PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="38ac7-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="38ac7-110">Stellen Sie über Exchange Online PowerShell eine direkte Verbindung zu einem geografischem Standort her.</span><span class="sxs-lookup"><span data-stu-id="38ac7-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="38ac7-111">Normalerweise verbindet sich Exchange Online PowerShell mit dem zentralen geografischen Standort.</span><span class="sxs-lookup"><span data-stu-id="38ac7-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="38ac7-112">Sie können sich aber auch direkt mit geografischen Satellitenstandorten verbinden.</span><span class="sxs-lookup"><span data-stu-id="38ac7-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="38ac7-113">Aufgrund von Leistungsverbesserungen empfehlen wir, sich direkt mit dem geografischen Satellitenstandort zu verbinden, wenn Sie nur Benutzer an diesem geografischem Standort verwalten.</span><span class="sxs-lookup"><span data-stu-id="38ac7-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="38ac7-114">Die Anforderungen für die Installation und Verwendung des EXO V2-Moduls sind in [Installieren und Verwalten des EXO V2-Moduls](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="38ac7-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="38ac7-115">Um Exchange Online PowerShell mit einem bestimmten geografischen Speicherort zu verbinden, unterscheidet sich der Parameter *ConnectionUri* von den regulären Verbindungsanweisungen.</span><span class="sxs-lookup"><span data-stu-id="38ac7-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="38ac7-116">Die restlichen Befehle und Werte sind identisch.</span><span class="sxs-lookup"><span data-stu-id="38ac7-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="38ac7-117">Insbesondere müssen Sie den `?email=<emailaddress>` Wert am Ende des _ConnectionUri_ -Werts hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="38ac7-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="38ac7-118">`<emailaddress>` ist die e-Mail-Adresse eines **beliebigen** Postfachs am geografischen Zielspeicherort.</span><span class="sxs-lookup"><span data-stu-id="38ac7-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="38ac7-119">Ihre Berechtigungen für dieses Postfach oder die Beziehung zu Ihren Anmeldeinformationen sind kein Faktor; die e-Mail-Adresse sagt Exchange Online PowerShell einfach aus, wo eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="38ac7-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="38ac7-120">Microsoft 365 oder Microsoft 365 gcc-Kunden benötigen normalerweise den _ConnectionUri_ -Parameter nicht zum Herstellen einer Verbindung mit Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38ac7-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="38ac7-121">Um jedoch eine Verbindung mit einem bestimmten geografischen Standort herzustellen, müssen Sie den _ConnectionUri_ -Parameter verwenden, damit Sie `?email=<emailaddress>` den Wert verwenden können.</span><span class="sxs-lookup"><span data-stu-id="38ac7-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-using-multi-factor-authentication-mfa"></a><span data-ttu-id="38ac7-122">Herstellen einer Verbindung mit einem geografischen Standort in Exchange Online PowerShell mithilfe der mehrstufigen Authentifizierung (MFA)</span><span class="sxs-lookup"><span data-stu-id="38ac7-122">Connect to a geo location in Exchange Online PowerShell using multi-factor authentication (MFA)</span></span>

1. <span data-ttu-id="38ac7-123">Laden Sie in einem Windows PowerShell-Fenster das EXO V2-Modul, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="38ac7-123">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="38ac7-124">Im folgenden Beispiel ist admin@contoso.onmicrosoft.com das Administratorkonto, und der geografische Zielspeicherort befindet sich in der Olga@contoso.onmicrosoft.com des Postfachs.</span><span class="sxs-lookup"><span data-stu-id="38ac7-124">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

  ```powershell
  Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
  ```

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-without-using-mfa"></a><span data-ttu-id="38ac7-125">Herstellen einer Verbindung mit einem geografischen Standort in Exchange Online PowerShell ohne Verwendung von MFA</span><span class="sxs-lookup"><span data-stu-id="38ac7-125">Connect to a geo location in Exchange Online PowerShell without using MFA</span></span>

1. <span data-ttu-id="38ac7-126">Laden Sie in einem Windows PowerShell-Fenster das EXO V2-Modul, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="38ac7-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="38ac7-127">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="38ac7-127">Run the following command:</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

   <span data-ttu-id="38ac7-128">Geben Sie im angezeigten Dialogfeld **Bei Windows PowerShell anmelden** Ihr Geschäfts-, Schul- oder Unikonto und das Kennwort ein und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="38ac7-128">In the **Windows PowerShell Credential Request** dialog box that appears, type your work or school account and password, and then click **OK**.</span></span>

3. <span data-ttu-id="38ac7-129">Im folgenden Beispiel ist der geografische Zielspeicherort der Post Fach Olga@contoso.onmicrosoft.com gespeichert.</span><span class="sxs-lookup"><span data-stu-id="38ac7-129">In the following example, the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -Credential $UserCredential -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="38ac7-130">Anzeigen der verfügbaren geografischen Standorte, die in Ihrer Exchange Online-Organisation konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="38ac7-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="38ac7-131">Um die Liste der konfigurierten geografischen Standorte in Microsoft 365 Multi-Geo anzuzeigen, führen Sie den folgenden Befehl in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="38ac7-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="38ac7-132">Anzeigen des zentralen geografischen Standorts für Ihre Exchange Online-Organisation</span><span class="sxs-lookup"><span data-stu-id="38ac7-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="38ac7-133">Um den zentralen geografischen Standort Ihres Mandanten anzuzeigen, führen Sie den folgenden Befehl in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="38ac7-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="38ac7-134">Suchen des geografischen Standorts eines Postfachs</span><span class="sxs-lookup"><span data-stu-id="38ac7-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="38ac7-135">Die **Get-Mailbox** cmdlet in Exchange Online PowerShell zeigt die folgenden Multi-Geo-bezogenen Eigenschaften für Postfächer:</span><span class="sxs-lookup"><span data-stu-id="38ac7-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="38ac7-136">**Datenbank**: Die ersten 3 Buchstaben des Datenbanknamens entsprechen dem Geo-Code, der Ihnen mitteilt, wo sich das Postfach derzeit befindet.</span><span class="sxs-lookup"><span data-stu-id="38ac7-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="38ac7-137">Für Online-Archivpostfächer sollte die **Archivdatenbank** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="38ac7-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="38ac7-138">**MailboxRegion**: Gibt den geografischen Standortcode an, der vom Administrator festgelegt wurde (synchronisiert von **PreferredDataLocation** in Azure AD).</span><span class="sxs-lookup"><span data-stu-id="38ac7-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="38ac7-139">**MailboxRegionLastUpdateTime**: Gibt an, wann MailboxRegion zuletzt aktualisiert wurde (automatisch oder manuell).</span><span class="sxs-lookup"><span data-stu-id="38ac7-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="38ac7-140">Um diese Eigenschaften für ein Postfach anzuzeigen, verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="38ac7-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="38ac7-141">Um beispielsweise die geografische Information für das Postfach chris@contoso.onmicrosoft.com anzuzeigen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="38ac7-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="38ac7-142">Die Ausgabe des Befehls sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="38ac7-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="38ac7-143">Wenn der Geo-Standortcode im Datenbanknamen nicht mit dem **MailboxRegion** -Wert übereinstimmt, wird das Postfach automatisch in eine Verschiebungs Warteschlange verschoben und an den durch den **MailboxRegion** -Wert angegebenen geografischen Speicherort verschoben (Exchange Online sucht nach einem Missverhältnis zwischen diesen Eigenschaftswerten).</span><span class="sxs-lookup"><span data-stu-id="38ac7-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="38ac7-144">Verschieben eines bereits vorhandenen Nur-Cloud-Postfachs an einen bestimmten geografischen Standort</span><span class="sxs-lookup"><span data-stu-id="38ac7-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="38ac7-145">Ein Nur-Cloud-Benutzer ist ein Benutzer, der nicht über AAD Connect mit dem Mandanten synchronisiert ist.</span><span class="sxs-lookup"><span data-stu-id="38ac7-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="38ac7-146">Dieser Benutzer wurde direkt in Azure AD erstellt.</span><span class="sxs-lookup"><span data-stu-id="38ac7-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="38ac7-147">Verwenden der **Get-MsolUser** und **Set-MsolUser**-Cmdlets in Azure AD-Modul für Windows PowerShell zum Anzeigen oder Angeben des geografischen Standorts, wo ein Nur-Cloud-Postfach eines Benutzers gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="38ac7-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="38ac7-148">Um den **PreferredDataLocation**-Wert für einen Benutzer anzuzeigen, verwenden Sie diese Syntax in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="38ac7-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="38ac7-149">Um z. B. den **PreferredDataLocation**-Wert für den Benutzer michelle@contoso.onmicrosoft.com anzuzeigen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="38ac7-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="38ac7-150">Um den **PreferredDataLocation**-Wert für ein Nur-Cloud-Benutzerobjekt zu ändern, verwenden Sie die folgende Syntax in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="38ac7-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="38ac7-151">Um z. B. den **PreferredDataLocation**-Wert auf die Geodaten der  Europäischen Union (EUR) für den Benutzer michelle@contoso.onmicrosoft.com festzulegen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="38ac7-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="38ac7-152">Wie bereits erwähnt, können Sie dieses Verfahren nicht für synchronisierte Benutzerobjekte aus lokalen Active Directory verwenden.</span><span class="sxs-lookup"><span data-stu-id="38ac7-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="38ac7-153">Sie müssen den **PreferredDataLocation**-Wert in Active Directory ändern und mithilfe von AAD Connect synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="38ac7-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="38ac7-154">Weitere Informationen finden Sie unter [Azure Active Directory Connect-Synchronisierung: Konfigurieren von bevorzugten Datenspeicherorten für Microsoft 365-Ressourcen](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="38ac7-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="38ac7-155">Wie lange es dauert, ein Postfach an einen neuen geografischen Standort zu verschieben, hängt von mehreren Faktoren ab:</span><span class="sxs-lookup"><span data-stu-id="38ac7-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="38ac7-156">Der Größe und Art des Postfachs.</span><span class="sxs-lookup"><span data-stu-id="38ac7-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="38ac7-157">Der Anzahl der zu verschiebenden Postfächern.</span><span class="sxs-lookup"><span data-stu-id="38ac7-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="38ac7-158">Der Verfügbarkeit von Umzugsressourcen.</span><span class="sxs-lookup"><span data-stu-id="38ac7-158">The availability of move resources.</span></span>

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a><span data-ttu-id="38ac7-159">Dem Verschieben deaktivierter Postfächer, die einem Beweissicherungsverfahren unterliegen</span><span class="sxs-lookup"><span data-stu-id="38ac7-159">Move disabled mailboxes that are on Litigation Hold</span></span>

<span data-ttu-id="38ac7-160">Deaktivierte Postfächer, die einem Beweissicherungsverfahren unterliegen und für eDiscovery-Zwecke aufbewahrt werden, können nicht verschoben werden, indem ihr **PreferredDataLocation**-Wert in einen deaktivierten Status geändert wird.</span><span class="sxs-lookup"><span data-stu-id="38ac7-160">Disabled mailboxes on Litigation Hold that are preserved for eDiscovery purposes cannot be moved by changing their **PreferredDataLocation** value in their disabled state.</span></span> <span data-ttu-id="38ac7-161">So verschieben Sie ein deaktiviertes Postfach, das einem Beweissicherungsverfahren unterliegt:</span><span class="sxs-lookup"><span data-stu-id="38ac7-161">To move a disabled mailbox on litigation hold:</span></span>

1. <span data-ttu-id="38ac7-162">Weisen Sie dem Postfach vorübergehend eine Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="38ac7-162">Temporarily assign a license to the mailbox.</span></span>

2. <span data-ttu-id="38ac7-163">Ändern Sie die **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="38ac7-163">Change the **PreferredDataLocation**.</span></span>

3. <span data-ttu-id="38ac7-164">Entfernen Sie die Lizenz vom Postfach, nachdem es an den ausgewählten geografischen Standort verschoben wurde, um es wieder in den deaktivierten Status zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="38ac7-164">Remove the license from the mailbox after it has been moved to the selected geo location to put it back into the disabled state.</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="38ac7-165">Neue Cloud-Postfächer an einem bestimmten geografischen Standort erstellen</span><span class="sxs-lookup"><span data-stu-id="38ac7-165">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="38ac7-166">Um ein neues Postfach an einem bestimmten geografischen Standort zu erstellen, müssen Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="38ac7-166">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="38ac7-167">Konfigurieren Sie den **PreferredDataLocation**-Wert wie im vorherigen Abschnitt beschrieben, *bevor* das Postfach in Exchange Online erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="38ac7-167">Configure the **PreferredDataLocation** value as described in the previous section *before* the mailbox is created in Exchange Online.</span></span> <span data-ttu-id="38ac7-168">Konfigurieren Sie z. B. den **PreferredDataLocation**-Wert für einen Benutzer, bevor Sie eine Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="38ac7-168">For example, configure the **PreferredDataLocation** value on a user before assigning a license.</span></span>

- <span data-ttu-id="38ac7-169">Weisen Sie eine Lizenz zu, während Sie gleichzeitig den **PreferredDataLocation**-Wert festlegen.</span><span class="sxs-lookup"><span data-stu-id="38ac7-169">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="38ac7-170">Um einen neuen, nur für die Cloud lizenzierten Benutzer (nicht AAD Connect synchronisiert) an einem bestimmten geografischen Standorts zu erstellen, verwenden Sie die folgende Syntax in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="38ac7-170">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="38ac7-171">In diesem Beispiel erstellen Sie ein neues Benutzerkonto für Elizabeth Brunner mit den folgenden Werten:</span><span class="sxs-lookup"><span data-stu-id="38ac7-171">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="38ac7-172">Benutzerprinzipalname: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="38ac7-172">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="38ac7-173">Vorname: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="38ac7-173">First name: Elizabeth</span></span>
- <span data-ttu-id="38ac7-174">Nachname: Brunner</span><span class="sxs-lookup"><span data-stu-id="38ac7-174">Last name: Brunner</span></span>
- <span data-ttu-id="38ac7-175">Anzeigename: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="38ac7-175">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="38ac7-176">Kennwort: nach dem Zufallsprinzip generiert und in den Ergebnissen des Befehls angezeigt (da wir nicht den Parameter *Kennwort* verwenden)</span><span class="sxs-lookup"><span data-stu-id="38ac7-176">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="38ac7-177">Lizenz: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="38ac7-177">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="38ac7-178">Standort: Australien (AUS)</span><span class="sxs-lookup"><span data-stu-id="38ac7-178">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="38ac7-179">Weitere Informationen zum Erstellen neuer Benutzerkonten und Suchen von LicenseAssignment-Werten in Azure AD PowerShell finden Sie unter [Erstellen von Benutzerkonten mit PowerShell](create-user-accounts-with-microsoft-365-powershell.md) und [Anzeigen von Lizenzen und Diensten in PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="38ac7-179">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="38ac7-180">Wenn Sie Exchange Online PowerShell verwenden, um ein Postfach zu aktivieren, und das Postfach direkt in der Geo erstellt werden muss, die in **PreferredDataLocation** angegeben ist, müssen Sie ein Exchange Online-Cmdlet wie **Enable-Mailbox** oder **New-Mailbox** direkt gegen den Cloud-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="38ac7-180">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="38ac7-181">Wenn Sie das lokale Exchange-Cmdlet **Enable-RemoteMailbox** verwenden, wird das Postfach an dem geografischen Standort erstellt.</span><span class="sxs-lookup"><span data-stu-id="38ac7-181">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="38ac7-182">Integrieren vorhandener lokaler Postfächer an einem bestimmten geografischen Standort</span><span class="sxs-lookup"><span data-stu-id="38ac7-182">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="38ac7-183">Sie können die standardmäßigen Onboarding-Tools und -Prozesse verwenden, um ein Postfach von einer lokalen Exchange-Organisation zu Exchange Online zu migrieren, einschließlich des [Migrations-Dashboards im EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331) und des [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch)-Cmdlets in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38ac7-183">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="38ac7-184">Der erste Schritt besteht in der Überprüfung, ob für jedes zu integrierende Postfach ein Benutzerobjekt vorhanden ist und ob der korrekte **PreferredDataLocation**-Wert in Azure Active Directory konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="38ac7-184">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="38ac7-185">Die Onboarding-Tools berücksichtigen den **PreferredDataLocation**-Wert und migrieren die Postfächer direkt an den angegebenen geografischen Standorte.</span><span class="sxs-lookup"><span data-stu-id="38ac7-185">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="38ac7-186">Oder Sie können die folgenden Schritte ausführen, um Postfächer direkt an einem bestimmten geografischen Standort mit dem [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest)-Cmdlet in Exchange Online PowerShell zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="38ac7-186">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="38ac7-187">Überprüfen Sie, ob das Benutzerobjekt für jedes zu integrierende Postfach vorhanden ist und ob **PreferredDataLocation** in Azure AD auf den gewünschten Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="38ac7-187">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="38ac7-188">Der Wert von **PreferredDataLocation** wird mit dem Attribut **MailboxRegion** des entsprechenden E-Mail-Benutzerobjekts in Exchange Online synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="38ac7-188">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="38ac7-189">Verbinden Sie sich direkt mit dem spezifischen Satellitenstandort anhand der Verbindungsanweisungen weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="38ac7-189">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="38ac7-190">Speichern Sie in Exchange Online PowerShell die lokalen Administrator-Anmeldeinformationen, mit denen eine Postfachmigration in einer Variablen durchgeführt wird, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="38ac7-190">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="38ac7-191">Erstellen Sie in Exchange Online PowerShell einen neuen **New-MoveRequest**, ähnlich wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38ac7-191">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="38ac7-192">Wiederholen Sie Schritt 4 für jedes Postfach, das Sie vom lokalen Exchange zum geografischen Satellitenstandort migrieren müssen, mit dem Sie derzeit verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="38ac7-192">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="38ac7-193">Wenn Sie zusätzliche Postfächer an einen anderen geografischen Satellitenstandort migrieren müssen, wiederholen Sie die Schritte 2 bis 4 für jeden einzelnen Satellitenstandort.</span><span class="sxs-lookup"><span data-stu-id="38ac7-193">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="38ac7-194">Multi-Geo-Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="38ac7-194">Multi-geo reporting</span></span>

<span data-ttu-id="38ac7-195">**Multi-Geo-Verwendungsberichte** im Admin Center von Microsoft 365 zeigen die Anzahl der Benutzer nach geografischem Standort an.</span><span class="sxs-lookup"><span data-stu-id="38ac7-195">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="38ac7-196">Der Bericht zeigt die Verteilung der Benutzer für den aktuellen Monat und bietet Verlaufsdaten für die letzten 6 Monate.</span><span class="sxs-lookup"><span data-stu-id="38ac7-196">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="38ac7-197">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38ac7-197">See also</span></span>

[<span data-ttu-id="38ac7-198">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="38ac7-198">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
