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
description: Erfahren Sie, wie Sie Exchange Online Multi-Geo-Einstellungen in Ihrer Microsoft 365 mit PowerShell verwalten.
ms.openlocfilehash: c8f06318313c4192fc2b3a289727933c5a54f3ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905584"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="93d16-103">Verwalten von Exchange Online-Postfächern in einer Multi-Geo-Umgebung</span><span class="sxs-lookup"><span data-stu-id="93d16-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="93d16-104">Exchange Online PowerShell ist erforderlich, um Multi-Geo-Eigenschaften in Ihrer Umgebung Microsoft 365 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="93d16-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="93d16-105">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="93d16-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="93d16-106">Sie benötigen das [Microsoft Azure Active Directory PowerShell-Modul](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 oder später in v1.x, um die **PreferredDataLocation**-Eigenschaft an Benutzerobjekten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="93d16-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="93d16-107">Benutzerobjekte, die über AAD Connect mit AAD synchronisiert werden, können ihren **PreferredDataLocation**-Wert direkt über AAD PowerShell ändern lassen.</span><span class="sxs-lookup"><span data-stu-id="93d16-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="93d16-108">Nur-Cloud-Benutzerobjekte können über AAD PowerShell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="93d16-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="93d16-109">Wie Sie eine Verbindung mit Azure AD PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="93d16-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="93d16-110">In Exchange Online Multi-Geo-Umgebungen müssen Sie keine manuellen Schritte ausführen, um Ihrem Mandanten Geos hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="93d16-110">In Exchange Online multi-geo environments, you don't need to do any manual steps to add geos to your tenant.</span></span> <span data-ttu-id="93d16-111">Nachdem Sie den Message Center-Beitrag erhalten haben, in dem steht, dass Multi-Geo für Exchange Online bereit ist, sind alle verfügbaren Geos bereit und für Die Verwendung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="93d16-111">After you receive the Message Center post that says multi-geo is ready for Exchange Online, all available geos will be ready and configured for you to use.</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="93d16-112">Stellen Sie über Exchange Online PowerShell eine direkte Verbindung zu einem geografischem Standort her.</span><span class="sxs-lookup"><span data-stu-id="93d16-112">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="93d16-113">Normalerweise verbindet sich Exchange Online PowerShell mit dem zentralen geografischen Standort.</span><span class="sxs-lookup"><span data-stu-id="93d16-113">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="93d16-114">Sie können sich aber auch direkt mit geografischen Satellitenstandorten verbinden.</span><span class="sxs-lookup"><span data-stu-id="93d16-114">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="93d16-115">Aufgrund von Leistungsverbesserungen empfehlen wir, sich direkt mit dem geografischen Satellitenstandort zu verbinden, wenn Sie nur Benutzer an diesem geografischem Standort verwalten.</span><span class="sxs-lookup"><span data-stu-id="93d16-115">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="93d16-116">Die Anforderungen für die Installation und Verwendung des EXO V2-Moduls sind in [Installieren und Verwalten des EXO V2-Moduls](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="93d16-116">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="93d16-117">Wenn Sie Exchange Online PowerShell mit einem bestimmten geografischen Standort verbinden möchten, ist der *ConnectionUri-Parameter* anders als die regulären Verbindungsanweisungen.</span><span class="sxs-lookup"><span data-stu-id="93d16-117">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="93d16-118">Die restlichen Befehle und Werte sind identisch.</span><span class="sxs-lookup"><span data-stu-id="93d16-118">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="93d16-119">Insbesondere müssen Sie den Wert zum `?email=<emailaddress>` Ende des _ConnectionUri-Werts_ hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="93d16-119">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="93d16-120">`<emailaddress>` ist die E-Mail-Adresse **eines beliebigen** Postfachs am geografischen Zielspeicherort.</span><span class="sxs-lookup"><span data-stu-id="93d16-120">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="93d16-121">Ihre Berechtigungen für dieses Postfach oder die Beziehung zu Ihren Anmeldeinformationen sind kein Faktor. die E-Mail-Adresse teilt Exchange Online PowerShell mit, wo eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="93d16-121">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="93d16-122">Microsoft 365 oder Microsoft 365 GCC Kunden müssen normalerweise nicht den _ConnectionUri-Parameter_ verwenden, um eine Verbindung mit Exchange Online PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="93d16-122">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="93d16-123">Um jedoch eine Verbindung mit einem bestimmten geografischen Standort herzustellen, müssen Sie _den ConnectionUri-Parameter_ verwenden, damit Sie den `?email=<emailaddress>` Wert verwenden können.</span><span class="sxs-lookup"><span data-stu-id="93d16-123">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a><span data-ttu-id="93d16-124">Verbinden zu einem geografischen Standort in Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="93d16-124">Connect to a geo location in Exchange Online PowerShell</span></span>

<span data-ttu-id="93d16-125">Die folgenden Verbindungsanweisungen funktionieren für Konten, die für die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) konfiguriert sind oder nicht konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="93d16-125">The following connection instructions work for accounts that are or aren't configured for multi-factor authentication (MFA).</span></span>

1. <span data-ttu-id="93d16-126">Laden Sie in einem Windows PowerShell-Fenster das EXO V2-Modul, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="93d16-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="93d16-127">Im folgenden Beispiel ist admin@contoso.onmicrosoft.com Administratorkonto, und der geografische Zielspeicherort ist der Ort, an dem sich olga@contoso.onmicrosoft.com befindet.</span><span class="sxs-lookup"><span data-stu-id="93d16-127">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. <span data-ttu-id="93d16-128">Geben Sie das Kennwort für admin@contoso.onmicrosoft.com in der angezeigten Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="93d16-128">Enter the password for the admin@contoso.onmicrosoft.com in the prompt that appears.</span></span> <span data-ttu-id="93d16-129">Wenn das Konto für MFA konfiguriert ist, müssen Sie auch den Sicherheitscode eingeben.</span><span class="sxs-lookup"><span data-stu-id="93d16-129">If the account is configured for MFA, you also need to enter the security code.</span></span>

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="93d16-130">Anzeigen der verfügbaren geografischen Standorte, die in Ihrer Exchange Online-Organisation konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="93d16-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="93d16-131">Um die Liste der konfigurierten geografischen Standorte in Microsoft 365 Multi-Geo anzuzeigen, führen Sie den folgenden Befehl in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="93d16-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="93d16-132">Anzeigen des zentralen geografischen Standorts für Ihre Exchange Online-Organisation</span><span class="sxs-lookup"><span data-stu-id="93d16-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="93d16-133">Um den zentralen geografischen Standort Ihres Mandanten anzuzeigen, führen Sie den folgenden Befehl in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="93d16-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="93d16-134">Suchen des geografischen Standorts eines Postfachs</span><span class="sxs-lookup"><span data-stu-id="93d16-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="93d16-135">Die **Get-Mailbox** cmdlet in Exchange Online PowerShell zeigt die folgenden Multi-Geo-bezogenen Eigenschaften für Postfächer:</span><span class="sxs-lookup"><span data-stu-id="93d16-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="93d16-136">**Datenbank**: Die ersten 3 Buchstaben des Datenbanknamens entsprechen dem Geo-Code, der Ihnen mitteilt, wo sich das Postfach derzeit befindet.</span><span class="sxs-lookup"><span data-stu-id="93d16-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="93d16-137">Für Online-Archivpostfächer sollte die **Archivdatenbank** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="93d16-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="93d16-138">**MailboxRegion**: Gibt den geografischen Standortcode an, der vom Administrator festgelegt wurde (synchronisiert von **PreferredDataLocation** in Azure AD).</span><span class="sxs-lookup"><span data-stu-id="93d16-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="93d16-139">**MailboxRegionLastUpdateTime**: Gibt an, wann MailboxRegion zuletzt aktualisiert wurde (automatisch oder manuell).</span><span class="sxs-lookup"><span data-stu-id="93d16-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="93d16-140">Um diese Eigenschaften für ein Postfach anzuzeigen, verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="93d16-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="93d16-141">Um beispielsweise die geografische Information für das Postfach chris@contoso.onmicrosoft.com anzuzeigen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="93d16-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="93d16-142">Die Ausgabe des Befehls sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="93d16-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="93d16-143">Wenn der Geospeicherortcode im Datenbanknamen nicht mit dem **Wert MailboxRegion** übereinstimmen sollte, wird das Postfach automatisch in eine Standortverlagerungswarteschlange verschoben und an den geografischen Standort verschoben, der durch den **MailboxRegion-Wert** angegeben wird (Exchange Online sucht nach einer Nichtübereinstimmung zwischen diesen Eigenschaftswerten).</span><span class="sxs-lookup"><span data-stu-id="93d16-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="93d16-144">Verschieben eines bereits vorhandenen Nur-Cloud-Postfachs an einen bestimmten geografischen Standort</span><span class="sxs-lookup"><span data-stu-id="93d16-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="93d16-145">Ein Nur-Cloud-Benutzer ist ein Benutzer, der nicht über AAD Connect mit dem Mandanten synchronisiert ist.</span><span class="sxs-lookup"><span data-stu-id="93d16-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="93d16-146">Dieser Benutzer wurde direkt in Azure AD erstellt.</span><span class="sxs-lookup"><span data-stu-id="93d16-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="93d16-147">Verwenden der **Get-MsolUser** und **Set-MsolUser**-Cmdlets in Azure AD-Modul für Windows PowerShell zum Anzeigen oder Angeben des geografischen Standorts, wo ein Nur-Cloud-Postfach eines Benutzers gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="93d16-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="93d16-148">Um den **PreferredDataLocation**-Wert für einen Benutzer anzuzeigen, verwenden Sie diese Syntax in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="93d16-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="93d16-149">Um z. B. den **PreferredDataLocation**-Wert für den Benutzer michelle@contoso.onmicrosoft.com anzuzeigen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="93d16-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="93d16-150">Um den **PreferredDataLocation**-Wert für ein Nur-Cloud-Benutzerobjekt zu ändern, verwenden Sie die folgende Syntax in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="93d16-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="93d16-151">Um z. B. den **PreferredDataLocation**-Wert auf die Geodaten der  Europäischen Union (EUR) für den Benutzer michelle@contoso.onmicrosoft.com festzulegen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="93d16-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="93d16-152">Wie bereits erwähnt, können Sie dieses Verfahren nicht für synchronisierte Benutzerobjekte aus lokalem Active Directory verwenden.</span><span class="sxs-lookup"><span data-stu-id="93d16-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="93d16-153">Sie müssen den **PreferredDataLocation**-Wert in Active Directory ändern und mithilfe von AAD Connect synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="93d16-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="93d16-154">Weitere Informationen finden Sie unter [Azure Active Directory Connect-Synchronisierung: Konfigurieren von bevorzugten Datenspeicherorten für Microsoft 365-Ressourcen](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="93d16-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="93d16-155">Wie lange es dauert, ein Postfach an einen neuen geografischen Standort zu verschieben, hängt von mehreren Faktoren ab:</span><span class="sxs-lookup"><span data-stu-id="93d16-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="93d16-156">Der Größe und Art des Postfachs.</span><span class="sxs-lookup"><span data-stu-id="93d16-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="93d16-157">Der Anzahl der zu verschiebenden Postfächern.</span><span class="sxs-lookup"><span data-stu-id="93d16-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="93d16-158">Der Verfügbarkeit von Umzugsressourcen.</span><span class="sxs-lookup"><span data-stu-id="93d16-158">The availability of move resources.</span></span>

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a><span data-ttu-id="93d16-159">Verschieben eines inaktiven Postfachs in einen bestimmten geografischen Standort</span><span class="sxs-lookup"><span data-stu-id="93d16-159">Move an inactive mailbox to a specific geo</span></span>

<span data-ttu-id="93d16-160">Sie können inaktive Postfächer, die für Compliancezwecke beibehalten werden (z. B. Postfächer im Prozesssicherungsverfahren), nicht verschieben, indem Sie deren **PreferredDataLocation-Wert** ändern.</span><span class="sxs-lookup"><span data-stu-id="93d16-160">You can't move inactive mailboxes that are preserved for compliance purposes (for example, mailboxes on Litigation Hold) by changing their **PreferredDataLocation** value.</span></span> <span data-ttu-id="93d16-161">Gehen Sie wie folgt vor, um ein inaktives Postfach in einen anderen geografischen Standort zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="93d16-161">To move an inactive mailbox to a different geo, do the following steps:</span></span>

1. <span data-ttu-id="93d16-162">Stellen Sie das inaktive Postfach wiederher.</span><span class="sxs-lookup"><span data-stu-id="93d16-162">Recover the inactive mailbox.</span></span> <span data-ttu-id="93d16-163">Anweisungen finden Sie unter [Recover an inactive mailbox](../compliance/recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="93d16-163">For instructions, see [Recover an inactive mailbox](../compliance/recover-an-inactive-mailbox.md).</span></span>

2. <span data-ttu-id="93d16-164">Verhindern Sie, dass der Assistent für verwaltete Ordner das wiederhergestellte Postfach verarbeitet, indem er den Namen, den Alias, das Konto oder die E-Mail-Adresse des Postfachs ersetzt und den folgenden Befehl \<MailboxIdentity\> in [Exchange Online PowerShell ausführen:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="93d16-164">Prevent the Managed Folder Assistant from processing the recovered mailbox by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. <span data-ttu-id="93d16-165">Weisen Sie **Exchange Online Plan 2-Lizenz** dem wiederhergestellten Postfach zu.</span><span class="sxs-lookup"><span data-stu-id="93d16-165">Assign an **Exchange Online Plan 2** license to the recovered mailbox.</span></span> <span data-ttu-id="93d16-166">Dieser Schritt ist erforderlich, um das Postfach wieder im Prozesssicherungsverfahren zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="93d16-166">This step is required to place the mailbox back on Litigation Hold.</span></span> <span data-ttu-id="93d16-167">Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](../admin/manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="93d16-167">For instructions, see [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).</span></span>

4. <span data-ttu-id="93d16-168">Konfigurieren Sie **den PreferredDataLocation-Wert** für das Postfach wie im vorherigen Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="93d16-168">Configure the **PreferredDataLocation** value on the mailbox as described in the previous section.</span></span>

5. <span data-ttu-id="93d16-169">Nachdem Sie bestätigt haben, dass das Postfach an den neuen geografischen Speicherort verschoben wurde, setzen Sie das wiederhergestellte Postfach wieder in das Prozesssicherungsverfahren ein.</span><span class="sxs-lookup"><span data-stu-id="93d16-169">After you've confirmed that the mailbox has moved to the new geo location, place the recovered mailbox back on Litigation Hold.</span></span> <span data-ttu-id="93d16-170">Anweisungen finden Sie unter [Place a mailbox on Litigation Hold](../compliance/create-a-litigation-hold.md#place-a-mailbox-on-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="93d16-170">For instructions, see [Place a mailbox on Litigation Hold](../compliance/create-a-litigation-hold.md#place-a-mailbox-on-litigation-hold).</span></span>

6. <span data-ttu-id="93d16-171">Nachdem Sie überprüft haben, ob das Verfahrensverfahren in Kraft ist, können Sie dem Assistenten für verwaltete Ordner erlauben, das Postfach erneut zu verarbeiten, indem Sie den Namen, den Alias, das Konto oder die E-Mail-Adresse des Postfachs ersetzen und den folgenden Befehl \<MailboxIdentity\> in [Exchange Online PowerShell ausführen:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="93d16-171">After verifying that the Litigation Hold is in place, allow the Managed Folder Assistant to process the mailbox again by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. <span data-ttu-id="93d16-172">Machen Sie das Postfach erneut inaktiv, indem Sie das Benutzerkonto entfernen, das dem Postfach zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="93d16-172">Make the mailbox inactive again by removing the user account that's associated with the mailbox.</span></span> <span data-ttu-id="93d16-173">Anweisungen finden Sie unter [Löschen eines Benutzers aus Ihrer Organisation](../admin/add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="93d16-173">For instructions, see [Delete a user from your organization](../admin/add-users/delete-a-user.md).</span></span> <span data-ttu-id="93d16-174">In diesem Schritt wird auch die Exchange Online Plan 2-Lizenz für andere Zwecke veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="93d16-174">This step also releases the Exchange Online Plan 2 license for other uses.</span></span>

<span data-ttu-id="93d16-175">**Hinweis**: Wenn Sie ein inaktives Postfach an einen anderen geografischen Speicherort verschieben, können Sie sich auf die Inhaltssuchergebnisse oder die Möglichkeit auswirken, das Postfach vom früheren geografischen Standort aus zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="93d16-175">**Note**: When you move an inactive mailbox to a different geo location, you might affect content search results or the ability to search the mailbox from the former geo location.</span></span> <span data-ttu-id="93d16-176">Weitere Informationen finden Sie unter [Durchsuchen und Exportieren von Inhalten in Multi-Geo-Umgebungen](../compliance/set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).</span><span class="sxs-lookup"><span data-stu-id="93d16-176">For more information, see [Searching and exporting content in Multi-Geo environments](../compliance/set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="93d16-177">Neue Cloud-Postfächer an einem bestimmten geografischen Standort erstellen</span><span class="sxs-lookup"><span data-stu-id="93d16-177">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="93d16-178">Um ein neues Postfach an einem bestimmten geografischen Standort zu erstellen, müssen Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="93d16-178">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="93d16-179">Konfigurieren Sie **den PreferredDataLocation-Wert,** wie im vorherigen Abschnitt Move  an existing [cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) beschrieben, bevor Sie das Postfach in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93d16-179">Configure the **PreferredDataLocation** value as described in the previous [Move an existing cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) section *before* you create the mailbox in Exchange Online.</span></span> <span data-ttu-id="93d16-180">Konfigurieren Sie beispielsweise den **PreferredDataLocation-Wert** für einen Benutzer, bevor Sie eine Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="93d16-180">For example, configure the **PreferredDataLocation** value on a user before you assign a license.</span></span>

- <span data-ttu-id="93d16-181">Weisen Sie eine Lizenz zu, während Sie gleichzeitig den **PreferredDataLocation**-Wert festlegen.</span><span class="sxs-lookup"><span data-stu-id="93d16-181">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="93d16-182">Um einen neuen, nur für die Cloud lizenzierten Benutzer (nicht AAD Connect synchronisiert) an einem bestimmten geografischen Standorts zu erstellen, verwenden Sie die folgende Syntax in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="93d16-182">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="93d16-183">In diesem Beispiel erstellen Sie ein neues Benutzerkonto für Elizabeth Brunner mit den folgenden Werten:</span><span class="sxs-lookup"><span data-stu-id="93d16-183">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="93d16-184">Benutzerprinzipalname: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="93d16-184">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="93d16-185">Vorname: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="93d16-185">First name: Elizabeth</span></span>
- <span data-ttu-id="93d16-186">Nachname: Brunner</span><span class="sxs-lookup"><span data-stu-id="93d16-186">Last name: Brunner</span></span>
- <span data-ttu-id="93d16-187">Anzeigename: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="93d16-187">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="93d16-188">Kennwort: nach dem Zufallsprinzip generiert und in den Ergebnissen des Befehls angezeigt (da wir nicht den Parameter *Kennwort* verwenden)</span><span class="sxs-lookup"><span data-stu-id="93d16-188">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="93d16-189">Lizenz: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="93d16-189">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="93d16-190">Standort: Australien (AUS)</span><span class="sxs-lookup"><span data-stu-id="93d16-190">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="93d16-191">Weitere Informationen zum Erstellen neuer Benutzerkonten und Suchen von LicenseAssignment-Werten in Azure AD PowerShell finden Sie unter [Erstellen von Benutzerkonten mit PowerShell](create-user-accounts-with-microsoft-365-powershell.md) und [Anzeigen von Lizenzen und Diensten in PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="93d16-191">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="93d16-192">Wenn Sie Exchange Online PowerShell verwenden, um ein Postfach zu aktivieren, und das Postfach direkt in der Geo erstellt werden muss, die in **PreferredDataLocation** angegeben ist, müssen Sie ein Exchange Online-Cmdlet wie **Enable-Mailbox** oder **New-Mailbox** direkt gegen den Cloud-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="93d16-192">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="93d16-193">Wenn Sie das lokale Exchange-Cmdlet **Enable-RemoteMailbox** verwenden, wird das Postfach an dem geografischen Standort erstellt.</span><span class="sxs-lookup"><span data-stu-id="93d16-193">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="93d16-194">Integrieren vorhandener lokaler Postfächer an einem bestimmten geografischen Standort</span><span class="sxs-lookup"><span data-stu-id="93d16-194">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="93d16-195">Sie können die standardmäßigen Onboarding-Tools und -Prozesse verwenden, um ein Postfach von einer lokalen Exchange-Organisation zu Exchange Online zu migrieren, einschließlich des [Migrations-Dashboards im EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331) und des [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch)-Cmdlets in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93d16-195">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="93d16-196">Der erste Schritt besteht in der Überprüfung, ob für jedes zu integrierende Postfach ein Benutzerobjekt vorhanden ist und ob der korrekte **PreferredDataLocation**-Wert in Azure Active Directory konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="93d16-196">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="93d16-197">Die Onboarding-Tools berücksichtigen den **PreferredDataLocation**-Wert und migrieren die Postfächer direkt an den angegebenen geografischen Standorte.</span><span class="sxs-lookup"><span data-stu-id="93d16-197">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="93d16-198">Oder Sie können die folgenden Schritte ausführen, um Postfächer direkt an einem bestimmten geografischen Standort mit dem [New-MoveRequest](/powershell/module/exchange/new-moverequest)-Cmdlet in Exchange Online PowerShell zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="93d16-198">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="93d16-199">Überprüfen Sie, ob das Benutzerobjekt für jedes zu integrierende Postfach vorhanden ist und ob **PreferredDataLocation** in Azure AD auf den gewünschten Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="93d16-199">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="93d16-200">Der Wert von **PreferredDataLocation** wird mit dem Attribut **MailboxRegion** des entsprechenden E-Mail-Benutzerobjekts in Exchange Online synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="93d16-200">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="93d16-201">Verbinden Sie sich direkt mit dem spezifischen Satellitenstandort anhand der Verbindungsanweisungen weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="93d16-201">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="93d16-202">Speichern Sie in Exchange Online PowerShell die lokalen Administrator-Anmeldeinformationen, mit denen eine Postfachmigration in einer Variablen durchgeführt wird, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="93d16-202">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="93d16-203">Erstellen Sie in Exchange Online PowerShell einen neuen **New-MoveRequest**, ähnlich wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="93d16-203">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="93d16-204">Wiederholen Sie Schritt 4 für jedes Postfach, das Sie vom lokalen Exchange zum geografischen Satellitenstandort migrieren müssen, mit dem Sie derzeit verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="93d16-204">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="93d16-205">Wenn Sie zusätzliche Postfächer an einen anderen geografischen Satellitenstandort migrieren müssen, wiederholen Sie die Schritte 2 bis 4 für jeden einzelnen Satellitenstandort.</span><span class="sxs-lookup"><span data-stu-id="93d16-205">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="93d16-206">Multi-Geo-Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="93d16-206">Multi-geo reporting</span></span>

<span data-ttu-id="93d16-207">**Multi-Geo-Verwendungsberichte** im Admin Center von Microsoft 365 zeigen die Anzahl der Benutzer nach geografischem Standort an.</span><span class="sxs-lookup"><span data-stu-id="93d16-207">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="93d16-208">Der Bericht zeigt die Verteilung der Benutzer für den aktuellen Monat und bietet Verlaufsdaten für die letzten 6 Monate.</span><span class="sxs-lookup"><span data-stu-id="93d16-208">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="93d16-209">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93d16-209">See also</span></span>

[<span data-ttu-id="93d16-210">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="93d16-210">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)