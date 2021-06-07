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
description: Innerhalb von 30 Tagen nach dem Löschen eines Benutzerkontos können Sie das Konto und alle Daten wiederherstellen, und der Benutzer kann sich mit demselben Konto anmelden.
ms.openlocfilehash: f849fe8e403aa9a72eccb4dd65665ec9f33618d1
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779650"
---
# <a name="restore-a-user"></a><span data-ttu-id="5fb80-103">Wiederherstellen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="5fb80-103">Restore a user</span></span>
   
<span data-ttu-id="5fb80-p101">Wenn Sie ein Benutzerkonto innerhalb von 30 Tagen nach dem Löschen wiederherstellen, werden das Benutzerkonto und alle zugehörigen Daten wiederhergestellt. Der Benutzer kann sich mit demselben Firmen- oder Schulkonto anmelden. Das Postfach wird vollständig wiederhergestellt. Wenn Sie herausfinden müssen, wie viel Zeit noch bleibt, um ein bestimmtes Benutzerkonto wiederherzustellen, [wenden Sie sich an uns](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="5fb80-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../../business-video/get-help-support.md).</span></span>
  
<span data-ttu-id="5fb80-108">Nachfolgend ein paar Tipps:</span><span class="sxs-lookup"><span data-stu-id="5fb80-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="5fb80-109">Stellen Sie sicher, dass Dem Konto Lizenzen zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="5fb80-109">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="5fb80-110">Wenn Ihr Unternehmen Active Directory verwendet, finden Sie Informationen zum Wiederherstellen eines Benutzerkontos unter [Problembehandlung gelöschter Benutzerkonten in Office 365.](/office365/troubleshoot/active-directory/restore-deleted-user-accounts)</span><span class="sxs-lookup"><span data-stu-id="5fb80-110">If your business uses Active Directory, for instrutcions on restoring a user account, see [How to troubleshoot deleted user accounts in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts).</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="5fb80-111">Wiederherstellen eines oder mehrerer Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="5fb80-111">Restore one or more user accounts</span></span>

<span data-ttu-id="5fb80-112">Sie müssen ein Microsoft 365 globaler Administrator oder Benutzerverwaltungsadministrator sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="5fb80-112">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 

1. <span data-ttu-id="5fb80-113">Wechseln Sie im Admin Center zur Seite **"Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">gelöschte Benutzer".</a></span><span class="sxs-lookup"><span data-stu-id="5fb80-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="5fb80-114">Wählen Sie auf der Seite **"Gelöschte Benutzer"** die Namen der Benutzer aus, die Sie wiederherstellen möchten, und wählen Sie dann **"Wiederherstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="5fb80-114">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
3. <span data-ttu-id="5fb80-115">Befolgen Sie die Aufforderungen, um ihr Kennwort festzulegen, und wählen Sie dann **Wiederherstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="5fb80-115">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="5fb80-116">Wenn der Benutzer erfolgreich wiederhergestellt wurde, wählen Sie **"E-Mail senden" aus, und schließen Sie**.</span><span class="sxs-lookup"><span data-stu-id="5fb80-116">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="5fb80-117">Wenn ein Namens- oder Proxyadressenkonflikt vorliegt, lesen Sie die nachstehenden Anweisungen, um zu erfahren, wie Sie diese Konten wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="5fb80-117">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="5fb80-118">Nachdem Sie einen Benutzer wiederhergestellt haben, stellen Sie sicher, dass Sie diesen benachrichtigen, dass sein Kennwort geändert wurde, und folgen Sie diesen.</span><span class="sxs-lookup"><span data-stu-id="5fb80-118">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="5fb80-119">Wiederherstellen eines Benutzers mit einem Benutzernamenskonflikt</span><span class="sxs-lookup"><span data-stu-id="5fb80-119">Restore a user that has a user name conflict</span></span>

<span data-ttu-id="5fb80-120">Ein Benutzernamenskonflikt tritt auf, wenn Sie ein Benutzerkonto löschen, ein neues Benutzerkonto mit demselben Benutzernamen (für denselben Benutzer oder für einen anderen Benutzer mit einem ähnlichen Namen) erstellen und dann später versuchen, das gelöschte Konto wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="5fb80-120">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="5fb80-p103">Um diesen Konflikt zu lösen, können Sie entweder das aktive Benutzerkonto durch das wiederherzustellende Konto ersetzen oder dem Konto, das Sie wiederherstellen, einen anderen Benutzernamen zuweisen, damit nicht zwei Konten mit demselben Benutzernamen vorhanden sind. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="5fb80-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>

1. <span data-ttu-id="5fb80-124">Wechseln Sie im Admin Center zur Seite **"Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">gelöschte Benutzer".</a></span><span class="sxs-lookup"><span data-stu-id="5fb80-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>
  
2. <span data-ttu-id="5fb80-125">Wählen Sie auf der Seite **"Gelöschte Benutzer"** die Namen der Benutzer aus, die Sie wiederherstellen möchten, und wählen Sie dann **"Wiederherstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="5fb80-125">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5fb80-p104">Wenn mindestens zwei Benutzer nicht wiederhergestellt werden können, wird in einer Fehlermeldung angezeigt, dass der Wiederherstellungsvorgang für einige Benutzer nicht erfolgreich ausgeführt wurde. Öffnen Sie das Protokoll, um anzuzeigen, welche Benutzer nicht wiederhergestellt wurden, und stellen Sie dann die entsprechenden Konten jeweils einzeln wieder her.</span><span class="sxs-lookup"><span data-stu-id="5fb80-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="5fb80-128">Folgen Sie den Aufforderungen, um das Kennwort festzulegen, und wählen Sie **"Wiederherstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="5fb80-128">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="5fb80-p105">Sie werden in einer Meldung darüber informiert, dass beim Wiederherstellen des Kontos ein Problem aufgetreten ist. Führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="5fb80-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="5fb80-p106">Brechen Sie den Wiederherstellungsvorgang ab, und benennen Sie den aktuellen aktiven Benutzer um. Versuchen Sie dann, den Wiederherstellungsvorgang erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5fb80-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="5fb80-133">OR, type a new primary email address for the user and select **Restore**.</span><span class="sxs-lookup"><span data-stu-id="5fb80-133">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="5fb80-134">Überprüfen Sie die Ergebnisse, und wählen Sie dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="5fb80-134">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="5fb80-135">Wiederherstellen eines Benutzers, der einen Proxyadressenkonflikt hat</span><span class="sxs-lookup"><span data-stu-id="5fb80-135">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="5fb80-p107">Ein Proxyadressenkonflikt tritt auf, wenn Sie ein Benutzerkonto löschen, das eine Proxyadresse enthält, dieselbe Proxyadresse einem anderen Konto zuweisen und dann versuchen, das gelöschte Konto wiederherzustellen. Führen Sie die nachstehenden Schritte aus, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="5fb80-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="5fb80-138">Sie müssen über [Administratorberechtigungen](about-admin-roles.md) in Microsoft 365 verfügen, um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="5fb80-138">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 

1. <span data-ttu-id="5fb80-139">Wechseln Sie im Admin Center zur Seite **"Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">gelöschte Benutzer".</a></span><span class="sxs-lookup"><span data-stu-id="5fb80-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="5fb80-140">Wählen Sie auf der Seite **Gelöschte Benutzer** den Benutzer aus, den Sie wiederherstellen möchten, und wählen Sie dann **Wiederherstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="5fb80-140">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="5fb80-141">Befolgen Sie auf der Seite **"Wiederherstellen"** die Anweisungen, um das Kennwort festzulegen, und wählen Sie **"Wiederherstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="5fb80-141">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="5fb80-142">Für den Benutzer, den Sie wiederherstellen, werden alle Konflikt verursachenden Proxyadressen automatisch entfernt.</span><span class="sxs-lookup"><span data-stu-id="5fb80-142">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="5fb80-143">Überprüfen Sie die Ergebnisse, und wählen Sie dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="5fb80-143">Review the results, and then select **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="5fb80-144">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="5fb80-144">Related content</span></span>

<span data-ttu-id="5fb80-145">[Löschen eines Benutzers](delete-a-user.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="5fb80-145">[Delete a user](delete-a-user.md) (article)</span></span>\
<span data-ttu-id="5fb80-146">[Zuweisen von Administratorrollen](assign-admin-roles.md) (Video)</span><span class="sxs-lookup"><span data-stu-id="5fb80-146">[Assign admin roles](assign-admin-roles.md) (video)</span></span>\
<span data-ttu-id="5fb80-147">[Zuweisen von Lizenzen zu Benutzern](../manage/assign-licenses-to-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="5fb80-147">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>
