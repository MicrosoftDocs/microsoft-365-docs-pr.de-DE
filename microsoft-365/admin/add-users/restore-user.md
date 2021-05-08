---
title: Wiederherstellen eines Benutzers
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Erfahren Sie, wie Sie gelöschte Benutzerkonten und alle zugeordneten Daten wiederherstellen.
ms.openlocfilehash: 9cdc4100f963ed450b50caa0f07a3863bc87992d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244032"
---
# <a name="restore-a-user"></a><span data-ttu-id="f0b10-103">Wiederherstellen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="f0b10-103">Restore a user</span></span>
   
<span data-ttu-id="f0b10-p101">Wenn Sie ein Benutzerkonto innerhalb von 30 Tagen nach dem Löschen wiederherstellen, werden das Benutzerkonto und alle zugehörigen Daten wiederhergestellt. Der Benutzer kann sich mit demselben Firmen- oder Schulkonto anmelden. Das Postfach wird vollständig wiederhergestellt. Wenn Sie herausfinden müssen, wie viel Zeit noch bleibt, um ein bestimmtes Benutzerkonto wiederherzustellen, [wenden Sie sich an uns](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="f0b10-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../contact-support-for-business-products.md).</span></span>
  
<span data-ttu-id="f0b10-108">Nachfolgend ein paar Tipps:</span><span class="sxs-lookup"><span data-stu-id="f0b10-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="f0b10-109">Stellen Sie sicher, dass Lizenzen verfügbar sind, die dem Konto zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="f0b10-109">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="f0b10-110">Wenn Ihr Unternehmen Active Directory verwendet, lesen Sie die unter [Behandeln von Problemen mit gelöschten Benutzerkonten in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md) aufgeführten Anweisungen zum Wiederherstellen eines Benutzerkontos.</span><span class="sxs-lookup"><span data-stu-id="f0b10-110">If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md) for instructions on restoring a user account.</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="f0b10-111">Wiederherstellen eines oder mehrerer Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="f0b10-111">Restore one or more user accounts</span></span>

<span data-ttu-id="f0b10-112">Sie müssen ein globaler Microsoft 365 oder Benutzerverwaltungsadministrator sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="f0b10-112">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 

1. <span data-ttu-id="f0b10-113">Wechseln Sie im Admin Center zur **Seite** Benutzer \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">gelöschte</a> Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f0b10-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="f0b10-114">Wählen Sie **auf der** Seite Gelöschte Benutzer die Namen der Benutzer aus, die Sie wiederherstellen möchten, und wählen Sie dann **Wiederherstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="f0b10-114">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
3. <span data-ttu-id="f0b10-115">Folgen Sie den Aufforderungen zum Festlegen ihres Kennworts, und wählen Sie dann **Wiederherstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="f0b10-115">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="f0b10-116">Wenn der Benutzer erfolgreich wiederhergestellt wurde, wählen Sie **E-Mail senden und schließen aus.**</span><span class="sxs-lookup"><span data-stu-id="f0b10-116">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="f0b10-117">Wenn ein Namens- oder Proxyadressenkonflikt vorliegt, lesen Sie die nachstehenden Anweisungen, um zu erfahren, wie Sie diese Konten wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="f0b10-117">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="f0b10-118">Nachdem Sie einen Benutzer wiederhergestellt haben, müssen Sie ihn darüber informieren, dass sich sein Kennwort geändert hat, und folgen Sie ihm.</span><span class="sxs-lookup"><span data-stu-id="f0b10-118">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="f0b10-119">Wiederherstellen eines Benutzers mit einem Benutzernamenskonflikt</span><span class="sxs-lookup"><span data-stu-id="f0b10-119">Restore a user that has a user name conflict</span></span>

<span data-ttu-id="f0b10-120">Ein Benutzernamenskonflikt tritt auf, wenn Sie ein Benutzerkonto löschen, ein neues Benutzerkonto mit demselben Benutzernamen (für denselben Benutzer oder für einen anderen Benutzer mit einem ähnlichen Namen) erstellen und dann später versuchen, das gelöschte Konto wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="f0b10-120">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="f0b10-p103">Um diesen Konflikt zu lösen, können Sie entweder das aktive Benutzerkonto durch das wiederherzustellende Konto ersetzen oder dem Konto, das Sie wiederherstellen, einen anderen Benutzernamen zuweisen, damit nicht zwei Konten mit demselben Benutzernamen vorhanden sind. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="f0b10-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>

1. <span data-ttu-id="f0b10-124">Wechseln Sie im Admin Center zur **Seite** Benutzer \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">gelöschte</a> Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f0b10-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>
  
2. <span data-ttu-id="f0b10-125">Wählen Sie **auf der Seite** Gelöschte Benutzer die Namen der Benutzer aus, die Sie wiederherstellen möchten, und wählen Sie dann **Wiederherstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="f0b10-125">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f0b10-p104">Wenn mindestens zwei Benutzer nicht wiederhergestellt werden können, wird in einer Fehlermeldung angezeigt, dass der Wiederherstellungsvorgang für einige Benutzer nicht erfolgreich ausgeführt wurde. Öffnen Sie das Protokoll, um anzuzeigen, welche Benutzer nicht wiederhergestellt wurden, und stellen Sie dann die entsprechenden Konten jeweils einzeln wieder her.</span><span class="sxs-lookup"><span data-stu-id="f0b10-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="f0b10-128">Folgen Sie den Aufforderungen zum Festlegen des Kennworts, und wählen Sie **Wiederherstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="f0b10-128">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="f0b10-p105">Sie werden in einer Meldung darüber informiert, dass beim Wiederherstellen des Kontos ein Problem aufgetreten ist. Führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="f0b10-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="f0b10-p106">Brechen Sie den Wiederherstellungsvorgang ab, und benennen Sie den aktuellen aktiven Benutzer um. Versuchen Sie dann, den Wiederherstellungsvorgang erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f0b10-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="f0b10-133">OR, geben Sie eine neue primäre E-Mail-Adresse für den Benutzer ein, und wählen Sie **Wiederherstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="f0b10-133">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="f0b10-134">Überprüfen Sie die Ergebnisse, und wählen Sie dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="f0b10-134">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="f0b10-135">Wiederherstellen eines Benutzers, der einen Proxyadressenkonflikt hat</span><span class="sxs-lookup"><span data-stu-id="f0b10-135">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="f0b10-p107">Ein Proxyadressenkonflikt tritt auf, wenn Sie ein Benutzerkonto löschen, das eine Proxyadresse enthält, dieselbe Proxyadresse einem anderen Konto zuweisen und dann versuchen, das gelöschte Konto wiederherzustellen. Führen Sie die nachstehenden Schritte aus, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="f0b10-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="f0b10-138">Dazu müssen [Sie über Administratorberechtigungen](about-admin-roles.md) Microsoft 365 verfügen.</span><span class="sxs-lookup"><span data-stu-id="f0b10-138">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 

1. <span data-ttu-id="f0b10-139">Wechseln Sie im Admin Center zur **Seite** Benutzer \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">gelöschte</a> Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f0b10-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="f0b10-140">Wählen Sie auf der Seite **Gelöschte Benutzer** den Benutzer aus, den Sie wiederherstellen möchten, und wählen Sie dann **Wiederherstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="f0b10-140">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="f0b10-141">Folgen Sie **auf** der Seite Wiederherstellen den Anweisungen zum Festlegen des Kennworts, und wählen Sie **Wiederherstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="f0b10-141">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="f0b10-142">Für den Benutzer, den Sie wiederherstellen, werden alle Konflikt verursachenden Proxyadressen automatisch entfernt.</span><span class="sxs-lookup"><span data-stu-id="f0b10-142">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="f0b10-143">Überprüfen Sie die Ergebnisse, und wählen Sie dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="f0b10-143">Review the results, and then select **Close**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f0b10-144">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="f0b10-144">Related articles</span></span>

[<span data-ttu-id="f0b10-145">Löschen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="f0b10-145">Delete a user</span></span>](delete-a-user.md)
