---
title: Microsoft 365 Multi-Geo-Mandantenkonfiguration
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: In diesem Artikel erfahren Sie, wie Sie Satellitenstandorte hinzufügen und Ihren Mandanten für Microsoft 365 Multi-Geo konfigurieren.
ms.openlocfilehash: 9176c66e8d0aa7e893ef137131147f8e0c85d3ac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923648"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a><span data-ttu-id="0ea3b-103">Microsoft 365 Multi-Geo-Mandantenkonfiguration</span><span class="sxs-lookup"><span data-stu-id="0ea3b-103">Microsoft 365 Multi-Geo tenant configuration</span></span>

<span data-ttu-id="0ea3b-104">Bevor Sie Ihren Mandanten für Microsoft 365 Multi-Geo konfigurieren, stellen Sie sicher, dass Sie [Plan für Microsoft 365 Multi-Geo](plan-for-multi-geo.md) gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-104">Before you configure your tenant for Microsoft 365 Multi-Geo, be sure you have read [Plan for Microsoft 365 Multi-Geo](plan-for-multi-geo.md).</span></span> <span data-ttu-id="0ea3b-105">Um die Schritte in diesem Artikel auszuführen, benötigen Sie eine Liste der geografischen Standorte, die Sie als Satellitenstandorte aktivieren möchten, und der Testbenutzer, die Sie für diese Standorte bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-105">To follow the steps in this article, you'll need a list of the geo locations that you want to enable as satellite locations, and the test users that you want to provision for those locations.</span></span>

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a><span data-ttu-id="0ea3b-106">Hinzufügen der Multi-Geo-Funktionen in Ihrem Microsoft 365-Plan zu Ihrem Mandanten</span><span class="sxs-lookup"><span data-stu-id="0ea3b-106">Add the Multi-Geo Capabilities in your Microsoft 365 plan to your tenant</span></span>

<span data-ttu-id="0ea3b-107">Wenn Sie Microsoft 365 Multi-Geo verwenden möchten, benötigen Sie den Plan _Multi-Geo-Funktionen in Microsoft 365_.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-107">To use Microsoft 365 Multi-Geo, you need the _Multi-Geo Capabilities in Microsoft 365_ plan.</span></span> <span data-ttu-id="0ea3b-108">Arbeiten Sie mit Ihrem Kontoteam, um diesen Plan zu Ihrem Mandanten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-108">Work with your account team to add this plan to your tenant.</span></span> <span data-ttu-id="0ea3b-109">Ihr Kontoteam setzt Sie mit dem entsprechenden Lizenzierungsexperten in Verbindung und konfiguriert Ihren Mandanten für Sie.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-109">Your account team will connect you with the appropriate licensing specialist and get your tenant configured.</span></span>

<span data-ttu-id="0ea3b-p103">Beachten Sie, dass der Plan für _Multi-Geo-Funktionen in Microsoft 365_ ein Serviceplan auf Benutzerebene ist. Sie benötigen eine Lizenz für jeden Benutzer, der an einem Satellitenstandort gehostet werden soll. Sie können mit der Zeit weitere Lizenzen hinzufügen, wenn Sie Benutzer in Ihrem Satellitenstandort hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-p103">Note that the _Multi-Geo Capabilities in Microsoft 365_ plan are a user-level service plan. You need a license for each user that you want to host in a satellite location. You can add more licenses over time as you add users in satellite locations.</span></span>

<span data-ttu-id="0ea3b-113">Nachdem der Plan _Multi-Geo-Funktionen in Microsoft 365_ Ihrem Mandanten bereitgestellt wurde, steht die Registerkarte **Geografische Standorte** im Admin Center von OneDrive sowie SharePoint zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-113">Once your tenant has been provisioned with the  _Multi-Geo Capabilities in Microsoft 365_ plan, the **Geo locations** tab will become available in the OneDrive and SharePoint admin centers.</span></span>

## <a name="add-satellite-locations-to-your-tenant"></a><span data-ttu-id="0ea3b-114">Hinzufügen von Satellitenstandorten zu Ihrem Mandanten</span><span class="sxs-lookup"><span data-stu-id="0ea3b-114">Add satellite locations to your tenant</span></span>

<span data-ttu-id="0ea3b-115">Sie müssen für jeden geografischen Standort, an dem Sie Daten speichern möchten, einen Satellitenstandort hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-115">You must add a satellite location for each geo location where you want to store data.</span></span> <span data-ttu-id="0ea3b-116">In der folgenden Tabelle werden verfügbare geografische Standorte angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0ea3b-116">Available geo locations are shown in the following table:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Screenshot der Seite mit geografischen Orten im SharePoint-Admin Center](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="0ea3b-118">So fügen Sie einen Satellitenstandort hinzu</span><span class="sxs-lookup"><span data-stu-id="0ea3b-118">To add a satellite location</span></span>

1. <span data-ttu-id="0ea3b-119">Öffnen Sie das SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-119">Open the SharePoint admin center.</span></span>

2. <span data-ttu-id="0ea3b-120">Navigieren Sie zu der Registerkarte **Geografische Standorte**.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-120">Navigate to the **Geo locations** tab.</span></span>

3. <span data-ttu-id="0ea3b-121">Klicken Sie auf **Ort hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-121">Click **Add location**.</span></span>

4. <span data-ttu-id="0ea3b-122">Wählen Sie den Standort aus, den Sie hinzufügen möchten, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-122">Select the location that you want to add, and then click **Next**.</span></span>

5. <span data-ttu-id="0ea3b-123">Geben Sie die Domäne ein, die Sie mit dem geografischen Standort verwenden möchten, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-123">Type the domain that you want to use with the geo location, and then click **Add**.</span></span>

6. <span data-ttu-id="0ea3b-124">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-124">Click **Close**.</span></span>

<span data-ttu-id="0ea3b-p105">Die Bereitstellung kann je nach Größe des Mandanten bis zu 72 Stunden dauern. Sobald die Bereitstellung für einen Satellitenstandort abgeschlossen ist, erhalten Sie eine E-Mail-Bestätigung. Wenn der neue geografische Standort blau auf der Karte auf der Registerkarte **Geografische Standorte** im OneDrive Admin Center angezeigt wird, können Sie mit dem Festlegen der bevorzugten Datenspeicherorte für die Benutzer für diesen geografischen Standort fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-p105">Provisioning may take from a few hours up to 72 hours, depending on the size of your tenant. Once provisioning of a satellite location has completed, you will receive an email confirmation. When the new geo location appears in blue on the map on the **Geo locations** tab in the OneDrive admin center, you can proceed to set users' preferred data location to that geo location.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0ea3b-p106">Ihr neuer Satellitenstandort wird mit Standardeinstellungen eingerichtet. Sie können diesen Satellitenstandort entsprechend den lokalen Complianceanforderungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-p106">Your new satellite location will be set up with default settings. This will allow you to configure that satellite location as appropriate for your local compliance needs.</span></span>

## <a name="setting-users-preferred-data-location"></a><span data-ttu-id="0ea3b-130">Festlegen des bevorzugten Datenspeicherorts für Benutzer</span><span class="sxs-lookup"><span data-stu-id="0ea3b-130">Setting users' preferred data location</span></span>
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

<span data-ttu-id="0ea3b-p107">Nachdem Sie die erforderlichen Satellitenstandorte aktiviert haben, können Sie Ihre Benutzerkonten für die Verwendung des bevorzugten Datenspeicherorts aktualisieren. Es wird empfohlen, auch dann einen bevorzugten Datenspeicherort für jeden Benutzer festzulegen, wenn dieser Benutzer am zentralen Datenspeicherort verbleibt.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-p107">Once you enable the needed satellite locations, you can update your user accounts to use the appropriate preferred data location. We recommend that you set a preferred data location for every user, even if that user is staying in the central location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ea3b-133">Wenn ein Standort, der noch nicht als Satellitenspeicherort oder zentraler Standort konfiguriert wurde, als bevorzugter Datenspeicherort eines Benutzers festgelegt wird, verwendet das System bei der Bereitstellung von OneDrive- und SharePoint-Websites sowie Gruppenpostfächern standardmäßig den zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-133">If a user's preferred data location is set to a location that has not been configured as a satellite location or the central location, the system will default to the central location when provisioning OneDrive and SharePoint sites and Group mailboxes.</span></span>

> [!TIP]
> <span data-ttu-id="0ea3b-134">Es wird empfohlen, die Prüfungen mit einem Testbenutzer oder einer kleinen Gruppe von Benutzern durchzuführen, bevor die Multi-Geo-Funktionen für Ihre Organisation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-134">We recommend that you begin validations with a test user or small group of users before rolling out multi-geo to your broader organization.</span></span>

<span data-ttu-id="0ea3b-135">In Azure Active Directory (Azure AD) gibt es zwei Arten von Benutzerobjekten: Nur-Cloud-Benutzer und synchronisierte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-135">In Azure Active Directory (Azure AD) there are two types of user objects: cloud only users and synchronized users.</span></span> <span data-ttu-id="0ea3b-136">Bitte befolgen Sie die Anweisungen für die entsprechende Benutzerart.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-136">Please follow the appropriate instructions for your type of user.</span></span>

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a><span data-ttu-id="0ea3b-137">Synchronisieren der bevorzugten Datenspeicherorte für Benutzer mithilfe von Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="0ea3b-137">Synchronize user's Preferred Data Location using Azure AD Connect</span></span> 

<span data-ttu-id="0ea3b-138">Wenn Benutzende Ihres Unternehmens von einem firmeninternen Active Directory-System mit Azure AD synchronisiert werden, muss ihre PreferredDataLocation in AD aufgefüllt und mit Azure AD synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-138">If your company's users are synchronized from an on-premises Active Directory system to Azure AD, their PreferredDataLocation must be populated in AD and synchronized to Azure AD.</span></span>

<span data-ttu-id="0ea3b-139">Folgen Sie dem Prozess in [Azure Active Directory Connect-Synchronisierung: Konfigurieren des bevorzugten Datenstandorts für Microsoft 365-Ressourcen](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation), um die Synchronisierung des bevorzugten Datenstandorts von Ihren lokalen Active Directory Domain Services (AD DS) mit Azure AD zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-139">Follow the process in [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) to configure Preferred Data Location sync from your on-premises Active Directory Domain Services (AD DS) to Azure AD.</span></span>

<span data-ttu-id="0ea3b-140">Wir empfehlen, die Einstellung des bevorzugten Datenspeicherorts von Benutzern im Rahmen des Standardworkflows für das Erstellen von Benutzern vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-140">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ea3b-141">Im Falle von Benutzern ohne bereitgestellte OneDrive-Umgebung sollten Sie nach der Synchronisierung des bevorzugten Datenspeicherortes mit Azure AD mindestens 24 Stunden warten, damit die Änderungen in Kraft treten, bevor sich die Benutzer bei OneDrive for Business anmelden.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-141">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is synchronized to Azure AD for the changes to propagate before the user logs in to OneDrive for Business.</span></span> <span data-ttu-id="0ea3b-142">(Durch Festlegen des bevorzugten Datenspeicherorts vor der Anmeldung des Benutzers für die Bereitstellung von OneDrive for Business wird sichergestellt, dass die neue OneDrive-Umgebung an dem richtigen Ort bereitgestellt wird.)</span><span class="sxs-lookup"><span data-stu-id="0ea3b-142">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

### <a name="setting-preferred-data-location-for-cloud-only-users"></a><span data-ttu-id="0ea3b-143">Festlegen des bevorzugten Datenspeicherorts für Nur-Cloud-Benutzer</span><span class="sxs-lookup"><span data-stu-id="0ea3b-143">Setting Preferred Data Location for cloud only users</span></span> 

<span data-ttu-id="0ea3b-144">Wenn die Benutzer Ihres Unternehmens nicht über ein lokales Active Directory-System mit Azure AD synchronisiert werden (d. h. wenn sie in Microsoft 365 oder Azure AD erstellt werden), muss der PDL über das Microsoft Azure Active Directory-Modul für Windows PowerShell festgelegt verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-144">If your company's users are not synchronized from an on-premises Active Directory system to Azure AD, meaning they are created in Microsoft 365 or Azure AD, then the PDL must be set using the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

<span data-ttu-id="0ea3b-145">Die Verfahren in diesem Abschnitt setzen das [Microsoft Azure Active Directory-Modul für Windows PowerShell](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0) voraus.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-145">The procedures in this section require the [Microsoft Azure Active Directory Module for Windows PowerShell Module](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0).</span></span> <span data-ttu-id="0ea3b-146">Wenn dieses Modul bereits installiert ist, stellen Sie sicher, dass Sie die neueste Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-146">If you already have this module installed, please ensure you update to the latest version.</span></span>

1.  <span data-ttu-id="0ea3b-147">[Stellen Sie eine Verbindung her, und melden Sie sich mit den Anmeldeinformationen eines globaler Administrators für Ihren Mandanten an](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0ea3b-147">[Connect and sign in](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) with a set of global administrator credentials for your tenant.</span></span>

2.  <span data-ttu-id="0ea3b-p111">Verwenden Sie das [Set-MsolUser](/powershell/msonline/v1/set-msoluser)-Cmdlet zum Festlegen des bevorzugten Datenspeicherorts für jeden Benutzer. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0ea3b-p111">Use the [Set-MsolUser](/powershell/msonline/v1/set-msoluser) cmdlet to set the preferred data location for each of your users. For example:</span></span>

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    <span data-ttu-id="0ea3b-p112">Sie können mithilfe des Get-MsolUser-Cmdlets prüfen, ob der bevorzugte Datenspeicherort korrekt festgelegt wurde. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0ea3b-p112">You can check to confirm that the preferred data location was updated properly by using the Get-MsolUser cmdlet. For example:</span></span>

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Screenshot des PowerShell-Fensters mit Set-MsolUser](../media/multi-geo-tenant-configuration-image3.png)

<span data-ttu-id="0ea3b-153">Wir empfehlen, die Einstellung des bevorzugten Datenspeicherorts von Benutzern im Rahmen des Standardworkflows für das Erstellen von Benutzern vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-153">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ea3b-154">Im Falle von neuen Benutzern ohne bereitgestellte OneDrive-Umgebung sollten Sie nach der Einstellung des bevorzugten Datenspeicherortes mindestens 24 Stunden warten, damit die Änderungen in Kraft treten, bevor sich die Benutzer bei OneDrive for Business anmelden.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-154">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is set for the changes to propagate before the user logs in to OneDrive.</span></span> <span data-ttu-id="0ea3b-155">(Durch Festlegen des bevorzugten Datenspeicherorts vor der Anmeldung des Benutzers für die Bereitstellung von OneDrive for Business wird sichergestellt, dass die neue OneDrive-Umgebung an dem richtigen Ort bereitgestellt wird.)</span><span class="sxs-lookup"><span data-stu-id="0ea3b-155">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a><span data-ttu-id="0ea3b-156">Bereitstellung von OneDrive und Auswirkungen auf den bevorzugten Datenspeicherort</span><span class="sxs-lookup"><span data-stu-id="0ea3b-156">OneDrive Provisioning and the effect of PDL</span></span>

<span data-ttu-id="0ea3b-157">Wenn für einen Benutzer bereits eine OneDrive-Website im Mandanten erstellt wurde, wird beim Festlegen des bevorzugten Speicherorts die vorhandene OneDrive-Bereitstellung nicht automatisch verschoben.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-157">If the user already has a OneDrive site created in the tenant, setting their PDL will not automatically move their existing OneDrive.</span></span> <span data-ttu-id="0ea3b-158">Informationen zum Verschieben von OneDrive eines Benutzers finden Sie unter [OneDrive for Business Geo Move](move-onedrive-between-geo-locations.md).</span><span class="sxs-lookup"><span data-stu-id="0ea3b-158">To move a user's OneDrive, see [OneDrive for Business Geo Move](move-onedrive-between-geo-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0ea3b-159">Exchange Online verlagert das Postfach des Benutzers automatisch, wenn sich die PLD ändert und die MailboxRegion nicht mehr mit dem Code für den geografischen Speicherort der Postfachdatenbank entspricht.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-159">Exchange Online automatically relocates the user's mailbox if the PLD changes and the MailboxRegion no longer matches the Mailbox Database Geo Location code.</span></span> <span data-ttu-id="0ea3b-160">Weitere Informationen finden Sie unter [Verwalten von Exchange Online-Postfächern in einer Multi-Geo-Umgebung](./administering-exchange-online-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="0ea3b-160">For more information, see [Administering Exchange Online mailboxes in a multi-geo environment](./administering-exchange-online-multi-geo.md).</span></span>

<span data-ttu-id="0ea3b-161">Wenn ein Benutzer nicht über eine OneDrive-Website innerhalb des Mandanten verfügt, wird OneDrive in Übereinstimmung mit den jeweiligen PDL-Einstellungen bereitgestellt, sofern der PDL des Benutzers einem der Satellitenstandorte des Unternehmens entspricht.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-161">If the user does not have a OneDrive site within the tenant, OneDrive will be provisioned for them in accordance to their PDL value, assuming the PDL for the user matches one of the company's satellite locations.</span></span>

## <a name="configuring-multi-geo-search"></a><span data-ttu-id="0ea3b-162">Konfigurieren der Multi-Geo-Suche</span><span class="sxs-lookup"><span data-stu-id="0ea3b-162">Configuring Multi-Geo search</span></span>

<span data-ttu-id="0ea3b-163">Der Multi-Geo-Mandant verfügt über aggregierte Suchfunktionen, mit denen eine Suchabfrage Ergebnisse von allen Orten innerhalb des Mandanten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-163">Your multi-geo tenant will have aggregate search capabilities allowing a search query to return results from anywhere within the tenant.</span></span>

<span data-ttu-id="0ea3b-164">Standardmäßig geben Suchen von diesen Einstiegspunkten aggregierte Ergebnisse zurück, auch wenn sich jeder Suchindex an dem jeweiligen relevanten geografischen Standort befindet:</span><span class="sxs-lookup"><span data-stu-id="0ea3b-164">By default, searches from these entry points will return aggregate results, even though each search index is located within its relevant geo location:</span></span>

- <span data-ttu-id="0ea3b-165">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="0ea3b-165">OneDrive for Business</span></span>

- <span data-ttu-id="0ea3b-166">Delve</span><span class="sxs-lookup"><span data-stu-id="0ea3b-166">Delve</span></span>

- <span data-ttu-id="0ea3b-167">SharePoint-Homepage</span><span class="sxs-lookup"><span data-stu-id="0ea3b-167">SharePoint Home</span></span>

- <span data-ttu-id="0ea3b-168">Suchcenter</span><span class="sxs-lookup"><span data-stu-id="0ea3b-168">Search Center</span></span>

<span data-ttu-id="0ea3b-169">Darüber hinaus können Multi-Geo-Suchfunktionen für Ihre benutzerdefinierte Suchanwendung konfiguriert werden, die die SharePoint-Suche-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-169">Additionally, multi-geo search capabilities can be configured for your custom search applications that use the SharePoint search API.</span></span>

<span data-ttu-id="0ea3b-170">Anweisungen, einschließlich Einschränkungen und Unterschiede, finden Sie unter [Konfigurieren der Suche für Multi-Geo in OneDrive for Business](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="0ea3b-170">Please review [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for instructions including any limitations and differences.</span></span>

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a><span data-ttu-id="0ea3b-171">Überprüfen der Microsoft 365 Multi-Geo-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0ea3b-171">Validating the Microsoft 365 Multi-Geo configuration</span></span>

<span data-ttu-id="0ea3b-172">Im Folgenden finden Sie einige grundlegende Anwendungsfälle, in denen eine Überprüfung vor dem Rollout von Microsoft 365 Multi-Geo im Unternehmen möglicherweise sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-172">Below are some basic use cases you may wish to include in your validation plan before broadly rolling out Microsoft 365 Multi-Geo to your company.</span></span> <span data-ttu-id="0ea3b-173">Nach Abschluss dieser Tests und zusätzlicher Anwendungsfälle, die für Ihr Unternehmen relevant sind, können Sie der ursprünglichen Pilotgruppe bei Bedarf weitere Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-173">Once you have completed these tests and any additional use cases that are relevant to your company, you may choose to move on to adding the users in your initial pilot group.</span></span>

<span data-ttu-id="0ea3b-174">**OneDrive for Business**</span><span class="sxs-lookup"><span data-stu-id="0ea3b-174">**OneDrive for Business**</span></span>

<span data-ttu-id="0ea3b-175">Wählen Sie OneDrive im Microsoft 365-Startprogramm aus und bestätigen Sie, dass Sie automatisch an den entsprechenden geografischen Standort des Benutzers (gemäß dessen PDL) weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-175">Select OneDrive from the Microsoft 365 app launcher and confirm that you are automatically directed to the appropriate geo location for the user, based on the user's PDL.</span></span> <span data-ttu-id="0ea3b-176">OneDrive for Business sollte jetzt an diesem Standort bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-176">OneDrive for Business should now begin provisioning at that location.</span></span> <span data-ttu-id="0ea3b-177">Versuchen Sie nach der Bereitstellung, einige Dokumente hoch- und herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-177">Once provisioned, try uploading and downloading some documents.</span></span>

<span data-ttu-id="0ea3b-178">**Mobile OneDrive-App**</span><span class="sxs-lookup"><span data-stu-id="0ea3b-178">**OneDrive Mobile App**</span></span>

<span data-ttu-id="0ea3b-179">Melden Sie sich bei Ihrer mobilen OneDrive-App mit den Anmeldeinformationen Ihres Testkontos an.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-179">Log into your OneDrive mobile App with your test account credentials.</span></span> <span data-ttu-id="0ea3b-180">Stellen Sie sicher, dass Ihre OneDrive for Business-Dateien angezeigt werden und mit denjenigen auf Ihrem Mobilgerät interagieren können.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-180">Confirm that you can see your OneDrive for Business files and can interact with them from your mobile device.</span></span>

<span data-ttu-id="0ea3b-181">**OneDrive-Synchronisierungsclient**</span><span class="sxs-lookup"><span data-stu-id="0ea3b-181">**OneDrive sync client**</span></span>

<span data-ttu-id="0ea3b-p119">Vergewissern Sie sich, dass der OneDrive-Synchronisierungsclient den geografischen Standort für OneDrive for Business nach Anmeldung automatisch erkennt. Wenn Sie den Synchronisierungsclient herunterladen müssen, klicken Sie in der OneDrive-Bibliothek auf **Synchronisieren**.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-p119">Confirm that the OneDrive sync client automatically detects your OneDrive for Business geo location upon login. If you need to download the sync client, you can click **Sync** in the OneDrive library.</span></span>

<span data-ttu-id="0ea3b-184">**Office-Anwendungen**</span><span class="sxs-lookup"><span data-stu-id="0ea3b-184">**Office applications**</span></span>

<span data-ttu-id="0ea3b-p120">Vergewissern Sie sich, dass Sie auf OneDrive for Business zugreifen können, indem Sie sich von einer Office-Anwendung wie Word aus anmelden. Öffnen Sie die Office-Anwendung, und wählen Sie „OneDrive – <TenantName>„. Office erkennt Ihren OneDrive-Ort und zeigt die Dateien, die Sie öffnen können.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-p120">Confirm that you can access OneDrive for Business by logging in from an Office application, such as Word. Open the Office application and select "OneDrive – <TenantName>". Office will detect your OneDrive location and show you the files that you can open.</span></span>

<span data-ttu-id="0ea3b-188">**Freigabe**</span><span class="sxs-lookup"><span data-stu-id="0ea3b-188">**Sharing**</span></span>

<span data-ttu-id="0ea3b-p121">Testen Sie die Freigabe von OneDrive-Dateien. Vergewissern Sie sich, dass die Personenauswahl alle SharePoint-Onlinebenutzer unabhängig vom geografischen Standort anzeigt.</span><span class="sxs-lookup"><span data-stu-id="0ea3b-p121">Try sharing OneDrive files. Confirm that the people picker shows you all your SharePoint online users regardless of their geo location.</span></span>