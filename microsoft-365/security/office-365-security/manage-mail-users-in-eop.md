---
title: Verwalten von E-Mail-Benutzern in EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Die Definition von E-Mail-Benutzern ist ein wichtiger Teil des Verwaltung des Exchange Online Protection-Diensts (EOP).
ms.openlocfilehash: 38beaa283d4fa120a75f11accf22861e6598d6e0
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38034356"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="8aea8-103">Verwalten von E-Mail-Benutzern in EOP</span><span class="sxs-lookup"><span data-stu-id="8aea8-103">Manage mail users in EOP</span></span>

<span data-ttu-id="8aea8-p101">Die Definition von E-Mail-Benutzern ist ein wichtiger Teil des Verwaltung des Exchange Online Protection-Diensts (EOP). Es gibt mehrere Möglichkeiten zur Verwaltung von Benutzern in EOP.</span><span class="sxs-lookup"><span data-stu-id="8aea8-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>

- <span data-ttu-id="8aea8-p102">**Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung**: Falls Ihr Unternehmen über vorhandene Benutzerkonten in einer lokalen Active Directory-Umgebung verfügt, können Sie diese Konten mit Azure Active Directory (AD) synchronisieren, wo eine Kopie der Konten in der Cloud gespeichert wird. Beim Synchronisieren vorhandener Benutzerkonten mit Azure Active Directory können Sie diese Benutzer im Bereich **Empfänger** von Exchange Admin Center (EAC) anzeigen. Es wird empfohlen, Verzeichnissynchronisierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8aea8-p102">**Use directory synchronization to manage mail users**: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud. When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC). Using directory synchronization is recommended.</span></span>

- <span data-ttu-id="8aea8-p103">**Verwalten von E-Mail-Benutzern über die Exchange Admin Center**: Hinzufügen und Verwalten von E-Mail-Benutzern direkt in der Exchange Admin Center. Dies ist der einfachste Weg, E-Mail-Benutzer hinzuzufügen, und hilfreich, um jeweils einen Benutzer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8aea8-p103">**Use the EAC to manage mail users**: Add and manage mail users directly in the EAC. This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>

- <span data-ttu-id="8aea8-111">**Verwenden von PowerShell zum Verwalten von e-Mail-Benutzern**: Hinzufügen und Verwalten von e-Mail-Benutzern in Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8aea8-111">**Use PowerShell to manage mail users**: Add and manage mail users by in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="8aea8-112">Diese Methode ist hilfreich, um mehrere Datensätze hinzuzufügen und Skripts zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8aea8-112">This method is useful for adding multiple records and creating scripts.</span></span>

> [!NOTE]
> <span data-ttu-id="8aea8-113">Sie können Benutzer im Microsoft 365 Admin Center hinzufügen, jedoch können diese Benutzer nicht als e-Mail-Empfänger verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8aea8-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8aea8-114">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="8aea8-114">Before you begin</span></span>

- <span data-ttu-id="8aea8-115">Informationen zum Öffnen des Exchange Admin Center finden Sie unter [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="8aea8-115">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="8aea8-p105">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Benutzer, Kontakte und Rollengruppen" im Thema [Featureberechtigungen in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="8aea8-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>

- <span data-ttu-id="8aea8-118">Beachten Sie, dass beim Erstellen von e-Mail-Benutzern mithilfe von Exchange Online Protection PowerShell-Cmdlets möglicherweise Einschränkungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="8aea8-118">Be aware that when creating mail users by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="8aea8-119">In den PowerShell-Befehlen in diesem Thema wird eine Batch Verarbeitungsmethode verwendet, die zu einer Ausbreitungs Verzögerung von ein paar Minuten führt, bevor die Ergebnisse der Befehle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8aea8-119">The PowerShell commands in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="8aea8-120">Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online Protection herstellen, können Sie unter [Verbinden mit Exchange Online Protection mithilfe von Remote-PowerShell](https://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx) nachlesen.</span><span class="sxs-lookup"><span data-stu-id="8aea8-120">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>

- <span data-ttu-id="8aea8-121">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="8aea8-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="8aea8-122">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="8aea8-122">Having problems?</span></span> <span data-ttu-id="8aea8-123">Fragen Sie im Forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) nach Hilfe.</span><span class="sxs-lookup"><span data-stu-id="8aea8-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="8aea8-124">Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="8aea8-124">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="8aea8-125">In diesem Abschnitt finden Sie weitere Informationen zum Verwalten von E-Mail-Benutzern mithilfe von Verzeichnissynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="8aea8-125">This section provides information about managing email users by using directory synchronization.</span></span>

<span data-ttu-id="8aea8-126">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="8aea8-126">**Notes**:</span></span>

- <span data-ttu-id="8aea8-127">Wenn Sie die Verzeichnissynchronisierung zum Verwalten Ihrer Empfänger verwenden, können Sie dennoch Benutzer im Microsoft 365 Admin Center hinzufügen und verwalten, Sie werden jedoch nicht mit Ihrer lokalen Active Directory synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="8aea8-127">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="8aea8-128">Dies liegt daran, dass die Verzeichnissynchronisierung nur Empfänger **von** Ihrem lokalen Active Directory **zur** Cloud synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="8aea8-128">This is because directory synchronization only syncs recipients **from** your on-premises Active Directory **to** the cloud.</span></span>

- <span data-ttu-id="8aea8-129">Die Verzeichnissynchronisierung wird für die Verwendung mit den folgenden Features empfohlen:</span><span class="sxs-lookup"><span data-stu-id="8aea8-129">Directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="8aea8-130">**Listen sicherer Absender und blockierter Absender in Outlook**: Wenn Sie mit dem Dienst synchronisiert werden, haben diese Listen Vorrang vor der Spamfilterung im Dienst.</span><span class="sxs-lookup"><span data-stu-id="8aea8-130">**Outlook safe sender and blocked sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="8aea8-131">Dadurch können Benutzer ihre eigene Liste sicherer und blockierter Absender auf Benutzer- oder Domänenbasis verwalten.</span><span class="sxs-lookup"><span data-stu-id="8aea8-131">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span>

  - <span data-ttu-id="8aea8-132">**Verzeichnisbasierte Edge-Blockierung (Blockierung)**: Weitere Informationen zu Blockierung finden Sie unter [Verwenden der verzeichnisbasierten Edge-Blockierung zum ablehnen von Nachrichten, die an ungültige Empfänger gesendet](https://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)werden.</span><span class="sxs-lookup"><span data-stu-id="8aea8-132">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span>

  - <span data-ttu-id="8aea8-133">**Spamquarantäne für Endbenutzer**: um auf die Spamquarantäne für Endbenutzer zugreifen zu können, benötigen Endbenutzer eine gültige Office 365 Benutzer-ID und ein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="8aea8-133">**End user spam quarantine**: In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="8aea8-134">EOP-Kunden, die lokale Postfächer schützen, müssen gültige E-Mail-Benutzer sein.</span><span class="sxs-lookup"><span data-stu-id="8aea8-134">EOP customers protecting on-premises mailboxes must be valid email users.</span></span>
 
  - <span data-ttu-id="8aea8-135">**Nachrichtenfluss Regeln**: Wenn Sie die Verzeichnissynchronisierung verwenden, werden Ihre vorhandenen Active Directory Benutzer und Gruppen automatisch in die Cloud hochgeladen, und Sie können dann Nachrichtenfluss Regeln (auch bekannt als Transportregeln) erstellen, die auf bestimmte Benutzer und/oder Gruppen abzielen, ohne Sie manuell über die Exchange-Verwaltungskonsole oder Exchange Online Protection PowerShell hinzufügen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="8aea8-135">**Mail flow rules**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="8aea8-136">Bitte beachten Sie, dass [dynamische Verteilungsgruppen](https://go.microsoft.com/fwlink/?LinkId=507569) nicht über die Verzeichnissynchronisierung synchronisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="8aea8-136">Note that [dynamic distribution groups](https://go.microsoft.com/fwlink/?LinkId=507569) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="8aea8-137">Rufen Sie die erforderlichen Berechtigungen ab, und bereiten Sie die Verzeichnissynchronisierung vor, wie unter [Vorbereiten der Verzeichnissynchronisierung](https://go.microsoft.com/fwlink/p/?LinkId=308908) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8aea8-137">Get the necessary permissions and prepare for directory synchronization, as described in [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span></span>

### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="8aea8-138">So synchronisieren Sie Benutzerverzeichnisse mit Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="8aea8-138">To synchronize user directories with Azure Active Directory Connect (AAD Connect)</span></span>

<span data-ttu-id="8aea8-139">Um Benutzer mit Azure Active Directory (AAD) zu synchronisieren, müssen Sie zunächst die **Verzeichnissynchronisierung aktivieren**, wie unter [Activate Directory Synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8aea8-139">To synchronize users to Azure Active Directory (AAD) you first have to **activate directory synchronization**, as described in [Activate directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span></span>

<span data-ttu-id="8aea8-140">Im nächsten Schritt wird die Installation und Konfiguration eines lokalen Computers ausgeführt, um Aad Connect auszuführen (falls Sie noch nicht über einen verfügen – was sich vor der Zeit lohnt).</span><span class="sxs-lookup"><span data-stu-id="8aea8-140">Next is the installation and configuration of an on-premises computer to run AAD Connect (if you don't already have one -- something worth checking ahead of time).</span></span> <span data-ttu-id="8aea8-141">Bei der [Einrichtung von Aad Connect, dem Thema Express Way,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) erfahren Sie, wie Sie Ihre Konten lokal und Azure AD mit Aad Connect einrichten und synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="8aea8-141">The [Setting up AAD Connect, the express way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) topic tells you how to setup and synchronize your accounts from on-premises to Azure AD with AAD Connect.</span></span>

<span data-ttu-id="8aea8-142">Bevor Sie diese Aufgabe ausführen, stellen Sie sicher, dass [Sie die Voraussetzungen erfüllen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), und [Wählen Sie den Installationstyp aus](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span><span class="sxs-lookup"><span data-stu-id="8aea8-142">But before you do that work, make certain [you meet prerequisites](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), and [choose your installation type](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span></span> <span data-ttu-id="8aea8-143">Der frühere Link ist zu einem kurzen Artikel für Express-Installationen.</span><span class="sxs-lookup"><span data-stu-id="8aea8-143">The earlier link is to a short article for express installs.</span></span> <span data-ttu-id="8aea8-144">Sie können auch Artikel zu [benutzerdefinierten Installationen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)oder zur [Pass-Through-Authentifizierung](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) finden, wenn Sie benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="8aea8-144">You can also find articles on [custom installations](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom), or [pass-through authentication](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) if they're needed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8aea8-p113">Wenn Sie den Konfigurationsassistent für Azure Active Directory-Synchronisierungstool abschließen, wird in Ihrer Active Directory-Gesamtstruktur das Konto **MSOL_AD_SYNC** erstellt. Dieses Konto wird zum Lesen und Synchronisieren der lokalen Active Directory-Informationen verwendet. Damit die Verzeichnissynchronisierung ordnungsgemäß ausgeführt wird, müssen Sie sicherstellen, dass TCP 443 auf dem lokalen Verzeichnissynchronisierungsserver geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="8aea8-p113">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="8aea8-148">Vergewissern Sie sich nach dem Konfigurieren der Synchronisierung, dass EoP ordnungsgemäß synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="8aea8-148">After configuring your sync, be sure to verify that EOP is synchronizing correctly.</span></span> <span data-ttu-id="8aea8-149">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Empfänger** \> **Kontakte**, und vergewissern Sie sich, dass die Liste der Benutzer in Ihrer lokalen Umgebung korrekt synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="8aea8-149">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>

## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="8aea8-150">Verwalten von E-Mail-Benutzern über die Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="8aea8-150">Use the EAC to manage mail users</span></span>

<span data-ttu-id="8aea8-151">In diesem Abschnitt finden Sie Informationen über das Hinzufügen und Verwalten von E-Mail-Benutzern direkt in der Exchange Admin Center.</span><span class="sxs-lookup"><span data-stu-id="8aea8-151">This section provides information about adding and managing email users directly in the EAC.</span></span>

### <a name="use-the-eac-to-add-a-mail-user"></a><span data-ttu-id="8aea8-152">Hinzufügen eines e-Mail-Benutzers mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="8aea8-152">Use the EAC to add a mail user</span></span>

1. <span data-ttu-id="8aea8-153">Erstellen Sie einen E-Mail-Benutzer, indem Sie in der Verwaltungskonsole **Empfänger** \> **Kontakte** aufrufen und dann auf **Neu +** klicken.</span><span class="sxs-lookup"><span data-stu-id="8aea8-153">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>

2. <span data-ttu-id="8aea8-154">Geben Sie auf der Seite **Neuer E-Mail-Benutzer** die folgenden Benutzerinformationen ein:</span><span class="sxs-lookup"><span data-stu-id="8aea8-154">On the **New mail user** page, enter the user's information, including the following:</span></span>

   ****

   |<span data-ttu-id="8aea8-155">**E-Mail-Benutzereigenschaft**</span><span class="sxs-lookup"><span data-stu-id="8aea8-155">**Mail user property**</span></span>|<span data-ttu-id="8aea8-156">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8aea8-156">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="8aea8-157">**Vorname**, **Initialen**, **Nachname**</span><span class="sxs-lookup"><span data-stu-id="8aea8-157">**First name**, **Initials**, and **Last name**</span></span>|<span data-ttu-id="8aea8-158">Geben Sie den vollständigen Benutzernamen in die entsprechenden Felder ein.</span><span class="sxs-lookup"><span data-stu-id="8aea8-158">Type the user's full name in the appropriate boxes.</span></span>|
   |<span data-ttu-id="8aea8-159">**Anzeigename**</span><span class="sxs-lookup"><span data-stu-id="8aea8-159">**Display name**</span></span>|<span data-ttu-id="8aea8-p115">Geben Sie einen Namen mit bis zu 64 Zeichen ein. Dieses Feld wird automatisch mit den Namen aufgefüllt, die Sie in den Feldern **Vorname**, **Initialen** und **Nachname** eingegeben haben. Der Anzeigename ist erforderlich.  </span><span class="sxs-lookup"><span data-stu-id="8aea8-p115">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.</span></span>|
   |<span data-ttu-id="8aea8-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8aea8-163">**Alias**</span></span>|<span data-ttu-id="8aea8-p116">Geben Sie einen eindeutigen Alias mit bis zu 64 Zeichen für den Benutzer ein. Der Aliasname ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8aea8-p116">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>|
   |<span data-ttu-id="8aea8-166">**Externe E-Mail-Adresse**</span><span class="sxs-lookup"><span data-stu-id="8aea8-166">**External email address**</span></span>|<span data-ttu-id="8aea8-167">Geben Sie die externe E-Mail-Adresse des Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="8aea8-167">Type the external email address of the user.</span></span>|
   |<span data-ttu-id="8aea8-168">**Benutzer-ID**</span><span class="sxs-lookup"><span data-stu-id="8aea8-168">**User id**</span></span>|<span data-ttu-id="8aea8-p117">Geben Sie den Namen ein, den der E-Mail-Benutzer verwenden soll, um sich beim Dienst anzumelden. Der Anmeldename des Benutzers setzt sich aus einem Benutzernamen auf der linken Seite des at-Zeichens (@) und einem Suffix auf der rechten Seite zusammen. Normalerweise ist das Suffix der Name der Domäne, in der sich das Benutzerkonto befindet.</span><span class="sxs-lookup"><span data-stu-id="8aea8-p117">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>|
   |<span data-ttu-id="8aea8-172">**Neues Kennwort**</span><span class="sxs-lookup"><span data-stu-id="8aea8-172">**New password**</span></span>|<span data-ttu-id="8aea8-p118">Geben Sie das Kennwort ein, das der E-Mail-Benutzer verwenden soll, um sich beim Dienst anzumelden. Stellen Sie sicher, dass das angegebene Kennwort den Anforderungen hinsichtlich Länge, Komplexität und Verlauf der Domäne entspricht, in der Sie das Benutzerkonto erstellen.</span><span class="sxs-lookup"><span data-stu-id="8aea8-p118">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>|
   |<span data-ttu-id="8aea8-175">**Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="8aea8-175">**Confirm password**</span></span>|<span data-ttu-id="8aea8-176">Geben Sie das Kennwort zur Bestätigung erneut ein.</span><span class="sxs-lookup"><span data-stu-id="8aea8-176">Retype the password to confirm it.</span></span>|

3. <span data-ttu-id="8aea8-p119">Klicken Sie auf **Speichern**, um den neuen E-Mail-Benutzer zu erstellen. Der neue Benutzer sollte in der Benutzerliste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8aea8-p119">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span>

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a><span data-ttu-id="8aea8-179">Bearbeiten oder Entfernen eines e-Mail-Benutzers mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="8aea8-179">Use the EAC to edit or remove a mail user</span></span>

- <span data-ttu-id="8aea8-180">Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.</span><span class="sxs-lookup"><span data-stu-id="8aea8-180">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="8aea8-181">Klicken Sie in der Liste der Benutzer auf den Benutzer, den Sie anzeigen oder ändern möchten, und wählen \*\*\*\* ![Sie dann Bearbeitungs](../media/ITPro-EAC-EditIcon.gif) Symbol bearbeiten aus, um die Benutzereinstellungen nach Bedarf zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8aea8-181">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="8aea8-182">Sie können den Benutzernamen, Aliasnamen oder die Kontaktinformationen ändern, und Sie können ausführliche Informationen zur Benutzerrolle in der Organisation eingeben.</span><span class="sxs-lookup"><span data-stu-id="8aea8-182">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="8aea8-183">Sie können auch einen Benutzer auswählen und dann Remove \*\*\*\* ![-Symbol](../media/ITPro-EAC-RemoveIcon.gif) entfernen auswählen, um es zu löschen.</span><span class="sxs-lookup"><span data-stu-id="8aea8-183">You can also select a user and then choose **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span>

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a><span data-ttu-id="8aea8-184">Verwenden von Exchange Online Protection PowerShell zum Verwalten von e-Mail-Benutzern</span><span class="sxs-lookup"><span data-stu-id="8aea8-184">Use Exchange Online Protection PowerShell to manage mail users</span></span>

<span data-ttu-id="8aea8-185">In diesem Abschnitt finden Sie Informationen dazu, wie Sie E-Mail-Benutzer mithilfe der Windows Remote-PowerShell hinzufügen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="8aea8-185">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>

### <a name="use-eop-powershell-to-add-a-mail-user"></a><span data-ttu-id="8aea8-186">Verwenden von EoP PowerShell zum Hinzufügen eines e-Mail-Benutzers</span><span class="sxs-lookup"><span data-stu-id="8aea8-186">Use EOP PowerShell to add a mail user</span></span>

<span data-ttu-id="8aea8-187">In diesem Beispiel wird anhand des [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser)-Cmdlets für Jeffrey Zeng ein E-Mail-aktiviertes Benutzerkonto mit den folgenden Angaben erstellt:</span><span class="sxs-lookup"><span data-stu-id="8aea8-187">This example uses the [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span>

- <span data-ttu-id="8aea8-188">Der Vorname ist "Jeffrey" und der Nachname ist "Zeng".</span><span class="sxs-lookup"><span data-stu-id="8aea8-188">The first name is Jeffrey and the last name is Zeng.</span></span>

- <span data-ttu-id="8aea8-189">Der Name ist "Jeffrey", und der Anzeigename ist "Jeffrey Zeng".</span><span class="sxs-lookup"><span data-stu-id="8aea8-189">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>

- <span data-ttu-id="8aea8-190">Der Alias ist "jeffreyz".</span><span class="sxs-lookup"><span data-stu-id="8aea8-190">The alias is jeffreyz.</span></span>

- <span data-ttu-id="8aea8-191">Die externe E-Mail-Adresse ist "jzeng@tailspintoys.com".</span><span class="sxs-lookup"><span data-stu-id="8aea8-191">The external email address is jzeng@tailspintoys.com.</span></span>

- <span data-ttu-id="8aea8-192">Der Office 365-Anmeldename ist "jeffreyz@contoso.onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="8aea8-192">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>

- <span data-ttu-id="8aea8-193">Das Kennwort lautet "Pa$$word1".</span><span class="sxs-lookup"><span data-stu-id="8aea8-193">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

<span data-ttu-id="8aea8-194">Um zu überprüfen, ob dies funktioniert hat, führen Sie den folgenden Befehl aus, um Informationen über den neuen e-Mail-Benutzer Jeffrey Zeng anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="8aea8-194">To verify that this worked, run the following command to display information about new mail user Jeffrey Zeng:</span></span>

```PowerShell
Get-User -Identity "Jeffrey Zeng"
```

<span data-ttu-id="8aea8-195">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span><span class="sxs-lookup"><span data-stu-id="8aea8-195">For detailed syntax and parameter information, see [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span></span>

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a><span data-ttu-id="8aea8-196">Verwenden von EoP PowerShell zum Bearbeiten der Eigenschaften eines e-Mail-Benutzers</span><span class="sxs-lookup"><span data-stu-id="8aea8-196">Use EOP PowerShell to edit the properties of a mail user</span></span>

<span data-ttu-id="8aea8-197">Verwenden Sie die Cmdlets [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) und [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser), um Eigenschaften für E-Mail-Benutzer anzuzeigen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8aea8-197">Use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) cmdlets to view or change properties for mail users.</span></span>

<span data-ttu-id="8aea8-198">In diesem Beispiel wird die externe E-Mail-Adresse für Pilar Pinella festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8aea8-198">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="8aea8-199">In diesem Beispiel wird die Eigenschaft "Company" für alle E-Mail-Benutzer in "Contoso" geändert.</span><span class="sxs-lookup"><span data-stu-id="8aea8-199">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="8aea8-200">Um zu überprüfen, ob dies funktioniert hat, verwenden Sie das [Get-Recipient-](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) Cmdlet, um die Änderungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8aea8-200">To verify that this worked, use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify the changes.</span></span> <span data-ttu-id="8aea8-201">(Beachten Sie, dass Sie für mehrere E-Mail-Kontakte mehrere Eigenschaften anzeigen können.)</span><span class="sxs-lookup"><span data-stu-id="8aea8-201">(Note that you can view multiple properties for multiple mail contacts.)</span></span>

```PowerShell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

<span data-ttu-id="8aea8-202">Führen Sie für das vorherige Beispiel, in dem die Eigenschaft "Company" für alle E-Mail-Benutzer auf "Contoso" festgelegt wurde, den folgenden Befehl aus, um die Änderungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="8aea8-202">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>

```PowerShell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="8aea8-203">Dieses Cmdlet verwendet eine Batchverarbeitungsmethode, die zu einer Laufzeitverzögerung von wenigen Minuten führt, bevor die Ergebnisse des Cmdlets sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="8aea8-203">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>

### <a name="use-eop-powershell-to-remove-a-mail-user"></a><span data-ttu-id="8aea8-204">Verwenden von EoP PowerShell zum Entfernen eines e-Mail-Benutzers</span><span class="sxs-lookup"><span data-stu-id="8aea8-204">Use EOP PowerShell to remove a mail user</span></span>

<span data-ttu-id="8aea8-205">In diesem Beispiel wird das [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser)-Cmdlet verwendet, um den Benutzer Jeffrey Zeng zu löschen:</span><span class="sxs-lookup"><span data-stu-id="8aea8-205">This example uses the [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) cmdlet to delete user Jeffrey Zeng:</span></span>

```PowerShell
Remove-EOPMailUser -Identity Jeffrey
```
<span data-ttu-id="8aea8-206">Führen Sie das Cmdlet [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) aus, um zu überprüfen, ob der e-Mail-Benutzer nicht mehr vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8aea8-206">To verify that this worked, run the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify that the mail user no longer exists.</span></span>

```PowerShell
Get-Recipient Jeffrey | Format-List
```
