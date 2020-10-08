---
title: Vorbereiten der Verzeichnissynchronisierung mit Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Beschreibt, wie Sie die Bereitstellung von Benutzern auf Microsoft 365 mithilfe der Verzeichnissynchronisierung und die langfristigen Vorteile der Verwendung dieser Methode vorbereiten.
ms.openlocfilehash: 79d2a7932867531849ce75f8452b91e8c7ddd7b1
ms.sourcegitcommit: 7e8151ff74cb1cfc0dd59fadcac423c338415d77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48390173"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="cb0c8-103">Vorbereiten der Verzeichnissynchronisierung mit Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb0c8-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="cb0c8-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="cb0c8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cb0c8-105">Zu den Vorteilen der Hybriden Identitäts-und Verzeichnissynchronisierung in Ihrer Organisation gehören:</span><span class="sxs-lookup"><span data-stu-id="cb0c8-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="cb0c8-106">Reduzieren der Verwaltungsprogramme in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="cb0c8-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="cb0c8-107">Optionales Aktivieren des Szenarios für einmaliges Anmelden</span><span class="sxs-lookup"><span data-stu-id="cb0c8-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="cb0c8-108">Automatisieren von Kontoänderungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb0c8-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="cb0c8-109">Weitere Informationen zu den Vorteilen der Verwendung der Verzeichnissynchronisierung finden Sie unter [Hybrid Identity with Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) und [Hybrid Identity for Microsoft 365](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="cb0c8-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="cb0c8-110">Die Verzeichnissynchronisierung erfordert jedoch die Planung und Vorbereitung, um sicherzustellen, dass Ihre Active Directory-Domänendienste (AD DS) mit dem Azure AD Mandanten Ihres Microsoft 365-Abonnements mit einem Minimum an Fehlern synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="cb0c8-111">Führen Sie die folgenden Schritte aus, um die besten Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="cb0c8-112">1. Aufgaben zur Verzeichnisbereinigung</span><span class="sxs-lookup"><span data-stu-id="cb0c8-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="cb0c8-113">Bevor Sie Ihre AD DS mit Ihrem Azure AD-Mandanten synchronisieren, müssen Sie Ihre AD DS bereinigen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb0c8-114">Wenn Sie AD DS Bereinigung vor der Synchronisierung nicht ausführen, kann dies zu erheblichen negativen Auswirkungen auf den Bereitstellungsprozess führen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="cb0c8-115">Es kann Tage oder sogar Wochen dauern, bis der Zyklus der Verzeichnissynchronisierung durchläuft, Fehler identifiziert und erneut synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="cb0c8-116">Führen Sie in Ihrem AD DS die folgenden Bereinigungsaufgaben für jedes Benutzerkonto aus, dem eine Microsoft 365-Lizenz zugewiesen wird:</span><span class="sxs-lookup"><span data-stu-id="cb0c8-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="cb0c8-117">Stellen Sie eine gültige und eindeutige e-Mail-Adresse im **proxyAddresses** -Attribut sicher.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="cb0c8-118">Entfernen Sie alle doppelten Werte im **proxyAddresses** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="cb0c8-119">Stellen Sie nach Möglichkeit einen gültigen und eindeutigen Wert für das **userPrincipalName** -Attribut im **Benutzer** Objekt des Benutzers sicher.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="cb0c8-120">Stellen Sie sicher, dass der AD DS UPN mit dem Azure AD UPN übereinstimmt, um eine optimale Synchronisierung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="cb0c8-121">Wenn ein Benutzer keinen Wert für das **userPrincipalName** -Attribut aufweist, muss das **User** -Objekt einen gültigen und eindeutigen Wert für das **sAMAccountName** -Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="cb0c8-122">Entfernen Sie alle doppelten Werte im **userPrincipalName** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="cb0c8-123">Stellen Sie für eine optimale Verwendung der globalen Adressliste (GAL) sicher, dass die Informationen in den folgenden Attributen des AD DS Benutzerkontos richtig sind:</span><span class="sxs-lookup"><span data-stu-id="cb0c8-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="cb0c8-124">givenName</span><span class="sxs-lookup"><span data-stu-id="cb0c8-124">givenName</span></span>
   - <span data-ttu-id="cb0c8-125">surname</span><span class="sxs-lookup"><span data-stu-id="cb0c8-125">surname</span></span>
   - <span data-ttu-id="cb0c8-126">displayName</span><span class="sxs-lookup"><span data-stu-id="cb0c8-126">displayName</span></span>
   - <span data-ttu-id="cb0c8-127">Position</span><span class="sxs-lookup"><span data-stu-id="cb0c8-127">Job Title</span></span>
   - <span data-ttu-id="cb0c8-128">Abteilung</span><span class="sxs-lookup"><span data-stu-id="cb0c8-128">Department</span></span>
   - <span data-ttu-id="cb0c8-129">Büro</span><span class="sxs-lookup"><span data-stu-id="cb0c8-129">Office</span></span>
   - <span data-ttu-id="cb0c8-130">Telefon (geschäftlich)</span><span class="sxs-lookup"><span data-stu-id="cb0c8-130">Office Phone</span></span>
   - <span data-ttu-id="cb0c8-131">Mobiltelefon</span><span class="sxs-lookup"><span data-stu-id="cb0c8-131">Mobile Phone</span></span>
   - <span data-ttu-id="cb0c8-132">Faxnummer</span><span class="sxs-lookup"><span data-stu-id="cb0c8-132">Fax Number</span></span>
   - <span data-ttu-id="cb0c8-133">Straße</span><span class="sxs-lookup"><span data-stu-id="cb0c8-133">Street Address</span></span>
   - <span data-ttu-id="cb0c8-134">Stadt/Ort</span><span class="sxs-lookup"><span data-stu-id="cb0c8-134">City</span></span>
   - <span data-ttu-id="cb0c8-135">Bundesland/Kanton</span><span class="sxs-lookup"><span data-stu-id="cb0c8-135">State or Province</span></span>
   - <span data-ttu-id="cb0c8-136">PLZ</span><span class="sxs-lookup"><span data-stu-id="cb0c8-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="cb0c8-137">Land oder Region</span><span class="sxs-lookup"><span data-stu-id="cb0c8-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="cb0c8-138">2. Verzeichnisobjekt-und Attribut Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="cb0c8-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="cb0c8-139">Für eine erfolgreiche Verzeichnissynchronisierung zwischen Ihrem AD DS und Microsoft 365 müssen die AD DS-Attribute ordnungsgemäß vorbereitet werden.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="cb0c8-140">Beispielsweise müssen Sie sicherstellen, dass bestimmte Zeichen nicht in bestimmten Attributen verwendet werden, die mit der Microsoft 365-Umgebung synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="cb0c8-141">Unerwartete Zeichen führen nicht dazu, dass die Verzeichnissynchronisierung fehlschlägt, aber möglicherweise wird eine Warnung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="cb0c8-142">Ungültige Zeichen führen dazu, dass die Verzeichnissynchronisierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="cb0c8-143">Die Verzeichnissynchronisierung schlägt auch fehl, wenn einige Ihrer AD DS Benutzer über ein oder mehrere doppelte Attribute verfügen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="cb0c8-144">Jeder Benutzer muss über eindeutige Attribute verfügen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="cb0c8-145">Die Attribute, die Sie vorbereiten müssen, sind hier aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="cb0c8-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="cb0c8-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="cb0c8-146">**displayName**</span></span>

  - <span data-ttu-id="cb0c8-147">Wenn das Attribut im User-Objekt vorhanden ist, wird es mit Microsoft 365 synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="cb0c8-148">Wenn dieses Attribut im User-Objekt vorhanden ist, muss es einen Wert dafür geben.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="cb0c8-149">Das heißt, das Attribut darf nicht leer sein.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="cb0c8-150">Maximale Anzahl der Zeichen: 256</span><span class="sxs-lookup"><span data-stu-id="cb0c8-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="cb0c8-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="cb0c8-151">**givenName**</span></span>

  - <span data-ttu-id="cb0c8-152">Wenn das Attribut im User-Objekt vorhanden ist, wird es mit Microsoft 365 synchronisiert, aber Microsoft 365 erfordert oder verwendet es nicht.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="cb0c8-153">Maximale Anzahl der Zeichen: 64</span><span class="sxs-lookup"><span data-stu-id="cb0c8-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="cb0c8-154">**mail**</span><span class="sxs-lookup"><span data-stu-id="cb0c8-154">**mail**</span></span>

  - <span data-ttu-id="cb0c8-155">Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb0c8-156">Wenn es doppelte Werte gibt, wird der erste Benutzer mit dem Wert synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="cb0c8-157">Nachfolgende Benutzer werden in Microsoft 365 nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="cb0c8-158">Sie müssen entweder den Wert in Microsoft 365 ändern oder beide Werte in AD DS ändern, damit beide Benutzer in Microsoft 365 angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="cb0c8-159">**mailnick Name** (Exchange-Alias)</span><span class="sxs-lookup"><span data-stu-id="cb0c8-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="cb0c8-160">Der Attributwert darf nicht mit einem Punkt (.) beginnen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="cb0c8-161">Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb0c8-162">Unterstriche ("_") im synchronisierten Namen gibt an, dass der ursprüngliche Wert dieses Attributs ungültige Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="cb0c8-163">Weitere Informationen zu diesem Attribut finden Sie unter [Exchange-Alias Attribut](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="cb0c8-163">For more information on this attribute, see [Exchange alias attribute](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="cb0c8-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="cb0c8-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="cb0c8-165">Mehrwertiges Attribut</span><span class="sxs-lookup"><span data-stu-id="cb0c8-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="cb0c8-166">Maximale Anzahl von Zeichen pro Wert: 256</span><span class="sxs-lookup"><span data-stu-id="cb0c8-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="cb0c8-167">Der Attributwert darf kein Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="cb0c8-168">Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="cb0c8-169">Ungültige Zeichen: \< \> ();, [] "'</span><span class="sxs-lookup"><span data-stu-id="cb0c8-169">Invalid characters: \< \> ( ) ; , [ ] " '</span></span>

    <span data-ttu-id="cb0c8-170">Beachten Sie, dass die ungültigen Zeichen auf die Zeichen nach dem typtrennzeichen und ":" angewendet werden, so dass SMTP:User@contso.com zulässig ist, aber SMTP:User:M@contoso.com nicht ist.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cb0c8-171">Alle SMTP-Adressen (Simple Mail Transport Protocol) sollten den e-Mail-Messagingstandards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="cb0c8-172">Wenn doppelte oder unerwünschte Adressen vorhanden sind, finden Sie im Hilfethema [Entfernen von doppelten und unerwünschten Proxyadressen in Exchange](https://go.microsoft.com/fwlink/?LinkId=293860).</span><span class="sxs-lookup"><span data-stu-id="cb0c8-172">If duplicate or unwanted addresses exist, see the Help topic [Removing duplicate and unwanted proxy addresses in Exchange](https://go.microsoft.com/fwlink/?LinkId=293860).</span></span>

- <span data-ttu-id="cb0c8-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="cb0c8-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="cb0c8-174">Maximale Anzahl der Zeichen: 20</span><span class="sxs-lookup"><span data-stu-id="cb0c8-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="cb0c8-175">Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="cb0c8-176">Ungültige Zeichen: [\ "|,/: \< \> + =;?</span><span class="sxs-lookup"><span data-stu-id="cb0c8-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="cb0c8-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="cb0c8-177">\* ']</span></span>
  - <span data-ttu-id="cb0c8-178">Wenn ein Benutzer ein ungültiges **sAMAccountName** -Attribut aufweist, aber über ein gültiges **userPrincipalName** -Attribut verfügt, wird das Benutzerkonto in Microsoft 365 erstellt.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="cb0c8-179">Wenn sowohl **sAMAccountName** als auch **userPrincipalName** ungültig sind, muss das AD DS **userPrincipalName** -Attribut aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="cb0c8-180">**SN** (Nachname)</span><span class="sxs-lookup"><span data-stu-id="cb0c8-180">**sn** (surname)</span></span>

  - <span data-ttu-id="cb0c8-181">Wenn das Attribut im User-Objekt vorhanden ist, wird es mit Microsoft 365 synchronisiert, aber Microsoft 365 erfordert oder verwendet es nicht.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="cb0c8-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="cb0c8-182">**targetAddress**</span></span>

    <span data-ttu-id="cb0c8-183">Es ist erforderlich, dass das **targetAddress** -Attribut (beispielsweise SMTP:Tom@contoso.com), das für den Benutzer aufgefüllt wird, in der Microsoft 365 GAL angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="cb0c8-184">Bei Messaging Migrationsszenarien von Drittanbietern wäre dies die Microsoft 365-Schemaerweiterung für den AD DS erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="cb0c8-185">Die Microsoft 365-Schemaerweiterung würde auch weitere nützliche Attribute zum Verwalten von Microsoft 365-Objekten hinzufügen, die mit einem Verzeichnissynchronisierungstool aus AD DS aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="cb0c8-186">Beispielsweise würde das **msExchHideFromAddressLists** -Attribut zum Verwalten von ausgeblendeten Postfächern oder Verteilergruppen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="cb0c8-187">Maximale Anzahl der Zeichen: 256</span><span class="sxs-lookup"><span data-stu-id="cb0c8-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="cb0c8-188">Der Attributwert darf kein Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="cb0c8-189">Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="cb0c8-190">Ungültige Zeichen: \ \< \> ();, [] "</span><span class="sxs-lookup"><span data-stu-id="cb0c8-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="cb0c8-191">Alle SMTP-Adressen (Simple Mail Transport Protocol) sollten den e-Mail-Messagingstandards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="cb0c8-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="cb0c8-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="cb0c8-193">Das **userPrincipalName** -Attribut muss das Anmeldeformat im Internet Format aufweisen, dem der Benutzername gefolgt von dem @-Zeichen (@) und einem Domänennamen folgt: beispielsweise user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="cb0c8-194">Alle SMTP-Adressen (Simple Mail Transport Protocol) sollten den e-Mail-Messagingstandards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="cb0c8-195">Die maximale Anzahl von Zeichen für das **userPrincipalName** -Attribut lautet 113.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="cb0c8-196">Eine bestimmte Anzahl von Zeichen ist vor und nach dem @-Zeichen wie folgt zulässig:</span><span class="sxs-lookup"><span data-stu-id="cb0c8-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="cb0c8-197">Maximale Anzahl von Zeichen für den Benutzernamen vor dem @-Zeichen (@): 64</span><span class="sxs-lookup"><span data-stu-id="cb0c8-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="cb0c8-198">Maximale Anzahl von Zeichen für den Domänennamen nach dem @-Zeichen (@): 48</span><span class="sxs-lookup"><span data-stu-id="cb0c8-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="cb0c8-199">Ungültige Zeichen: \% &amp; \* +/=?</span><span class="sxs-lookup"><span data-stu-id="cb0c8-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="cb0c8-200">{ } | \< \> ( ) ; : , [ ] " '</span><span class="sxs-lookup"><span data-stu-id="cb0c8-200">{ } | \< \> ( ) ; : , [ ] " '</span></span>
  - <span data-ttu-id="cb0c8-201">Zulässige Zeichen: a – z, a-z, 0 – 9, '.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="cb0c8-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="cb0c8-202">- _ !</span></span> <span data-ttu-id="cb0c8-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="cb0c8-203"># ^ ~</span></span>
  - <span data-ttu-id="cb0c8-204">Ein Umlaut ist ebenfalls ein ungültiges Zeichen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-204">An umlaut is also an invalid character.</span></span>
  - <span data-ttu-id="cb0c8-205">Das @-Zeichen ist in jedem **userPrincipalName** -Wert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="cb0c8-206">Das @-Zeichen darf nie das erste Zeichen in einem **userPrincipalName**-Wert sein.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="cb0c8-207">Der Benutzername darf nicht mit einem Punkt (.), einem kaufmännischen und- &amp; Zeichen (), einem Leerzeichen oder einem @-Zeichen enden.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="cb0c8-208">Der Benutzername darf keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="cb0c8-209">Routingfähige Domänen müssen verwendet werden; Beispielsweise können keine lokalen oder internen Domänen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="cb0c8-210">Unicode-Zeichen werden in Unterstriche umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="cb0c8-211">**userPrincipalName** darf keine doppelten Werte im Verzeichnis enthalten.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="cb0c8-212">3. Vorbereiten des userPrincipalName-Attributs</span><span class="sxs-lookup"><span data-stu-id="cb0c8-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="cb0c8-213">Active Directory wurde entwickelt, um es den Endbenutzern in Ihrer Organisation zu ermöglichen, sich mit **sAMAccountName** oder **userPrincipalName**bei Ihrem Verzeichnis anzumelden.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="cb0c8-214">Auf ähnliche Weise können sich Endbenutzer bei Microsoft 365 mit dem Benutzerprinzipalnamen (User Principal Name, UPN) Ihres Geschäfts-oder Schul Kontos anmelden.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="cb0c8-215">Die Verzeichnissynchronisierung versucht, neue Benutzer in Azure Active Directory mithilfe desselben UPN zu erstellen, der in Ihrem AD DS ist.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="cb0c8-216">Der UPN ist wie eine e-Mail-Adresse formatiert.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="cb0c8-217">In Microsoft 365 ist der UPN das Standardattribut, das zum Generieren der e-Mail-Adresse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="cb0c8-218">Es ist ganz einfach, **userPrincipalName** (in AD DS und in Azure AD) und die primäre e-Mail-Adresse in **proxyAddresses** auf unterschiedliche Werte festgelegt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="cb0c8-219">Wenn Sie auf unterschiedliche Werte festgelegt sind, kann es zu Verwirrung für Administratoren und Endbenutzer kommen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="cb0c8-220">Es empfiehlt sich, diese Attribute auszurichten, um Verwirrung zu verringern.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="cb0c8-221">Um die Anforderungen des einmaligen Anmeldens mit Active Directory-Verbunddienste (AD FS) 2.0 zu erfüllen, müssen Sie sicherstellen, dass die UPNs in Azure Active Directory und Ihre AD DS übereinstimmen und einen gültigen Domänennamespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="cb0c8-222">4. Hinzufügen eines alternativen UPN-Suffix zu AD DS</span><span class="sxs-lookup"><span data-stu-id="cb0c8-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="cb0c8-223">Möglicherweise müssen Sie ein alternatives UPN-Suffix hinzufügen, um die Unternehmensanmeldeinformationen des Benutzers der Microsoft 365-Umgebung zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="cb0c8-224">Ein UPN-Suffix ist der Teil eines Benutzerprinzipalnamens, der rechts vom Zeichen @ steht.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="cb0c8-225">UPNs, die für einmaliges Anmelden verwendet werden, können Buchstaben, Zahlen, Punkte, Bindestriche und Unterstriche enthalten, aber keine anderen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="cb0c8-226">Weitere Informationen zum Hinzufügen eines alternativen UPN-Suffix zu Active Directory finden Sie unter [Prepare for Directory Synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span><span class="sxs-lookup"><span data-stu-id="cb0c8-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="cb0c8-227">5. Übereinstimmung mit dem AD DS UPN mit dem Microsoft 365 UPN</span><span class="sxs-lookup"><span data-stu-id="cb0c8-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="cb0c8-228">Wenn Sie die Verzeichnissynchronisierung bereits eingerichtet haben, stimmt der UPN des Benutzers für Microsoft 365 möglicherweise nicht mit dem AD DS UPN des Benutzers überein, der in Ihrem AD DS definiert ist.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="cb0c8-229">Das kann vorkommen, wenn einem Benutzer vor der Überprüfung der Domäne schon eine Lizenz zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="cb0c8-230">Um dies zu beheben, verwenden Sie [PowerShell, um doppelten UPN zu beheben](https://go.microsoft.com/fwlink/p/?LinkId=396730) , um den UPN des Benutzers zu aktualisieren, um sicherzustellen, dass der Microsoft 365-UPN dem Benutzernamen und der Domäne des Unternehmens entspricht.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="cb0c8-231">Wenn Sie den UPN im AD DS aktualisieren und mit der Azure Active Directory-Identität synchronisieren möchten, müssen Sie die Lizenz des Benutzers in Microsoft 365 entfernen, bevor Sie die Änderungen in AD DS vornehmen.</span><span class="sxs-lookup"><span data-stu-id="cb0c8-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="cb0c8-232">Weitere Informationen finden Sie unter [Vorgehensweise Vorbereiten einer nicht routingfähigen Domäne (beispielsweise. Local Domain) für die Verzeichnissynchronisierung](prepare-a-non-routable-domain-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="cb0c8-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cb0c8-233">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cb0c8-233">Next steps</span></span>

<span data-ttu-id="cb0c8-234">Wenn Sie die Schritte 1 bis 5 oben ausgeführt haben, finden Sie weitere Informationen unter [Einrichten der Verzeichnissynchronisierung](set-up-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="cb0c8-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>
