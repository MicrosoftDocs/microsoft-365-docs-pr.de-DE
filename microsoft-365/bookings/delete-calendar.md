---
title: Löschen eines Buchungs Kalenders
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Verwenden Sie das Microsoft 365 Admin Center oder Windows PowerShell, um Buchungen Kalender zu löschen.
ms.openlocfilehash: 2fcb92cee18d709ef0e1fa3faa0246e622a9f9db
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126649"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="87408-103">Löschen eines Buchungs Kalenders in Buchungen</span><span class="sxs-lookup"><span data-stu-id="87408-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="87408-104">In diesem Artikel wird erklärt, wie Sie einen unerwünschten Buchungskalender löschen können.</span><span class="sxs-lookup"><span data-stu-id="87408-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="87408-105">Sie können den Buchungskalender im Microsoft 365 Admin Center löschen oder PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="87408-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="87408-106">Der Kalender "Buchungen" ist ein Postfach in Exchange Online, sodass Sie das entsprechende Benutzerkonto löschen, um den Buchungskalender zu löschen.</span><span class="sxs-lookup"><span data-stu-id="87408-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87408-107">Alle Buchungskalender, die Sie in 2017 oder früher erstellt haben, müssen mit den PowerShell-Anweisungen in diesem Thema gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="87408-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="87408-108">Alle Buchungskalender, die in 2018 oder danach erstellt wurden, können im Microsoft 365 Admin Center gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="87408-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="87408-109">Im Buchungskalender werden alle relevanten Informationen über diesen Buchungskalender und die Daten gespeichert, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="87408-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="87408-110">Unternehmensinformationen, Logo und Arbeitszeiten, die beim Erstellen des Buchungs Kalenders hinzugefügt wurden</span><span class="sxs-lookup"><span data-stu-id="87408-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="87408-111">Relevante Mitarbeiter und Dienste, die beim Erstellen des Buchungs Kalenders hinzugefügt wurden</span><span class="sxs-lookup"><span data-stu-id="87408-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="87408-112">Alle Buchungen und Zeit Termine, die dem Buchungskalender nach der Erstellung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="87408-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="87408-113">Sobald ein Buchungskalender gelöscht wurde, werden diese zusätzlichen Informationen ebenfalls endgültig gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="87408-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="87408-114">Löschen eines Buchungs Kalenders im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="87408-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="87408-115">Gehen Sie zum Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="87408-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="87408-116">Wählen Sie im Admin Center **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="87408-116">In the Admin center, select **Users**.</span></span>

   ![Abbildung der Benutzeroberfläche im Microsoft 365 Admin Center](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="87408-118">Wählen Sie auf der Seite **Aktive Benutzer** die Namen der Benutzer aus, die Sie löschen möchten, und wählen Sie dann **Benutzer löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="87408-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Image of Delete User UI in Microsoft 365 Admin Center](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="87408-120">Löschen eines Buchungs Kalenders mit Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="87408-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="87408-121">Voraussetzungen und Anleitungen für das Herstellen einer Verbindung mit Exchange Online PowerShell finden Sie unter [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) .</span><span class="sxs-lookup"><span data-stu-id="87408-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="87408-122">Um diese Schritte ausführen zu können, müssen Sie ein aktives Microsoft PowerShell-Befehlsfenster verwenden, das Sie ausgeführt haben, indem Sie die Option "als Administrator ausführen" auswählen.</span><span class="sxs-lookup"><span data-stu-id="87408-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="87408-123">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="87408-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="87408-124">Wenn Sie dazu aufgefordert werden, melden Sie sich mit den Anmeldeinformationen des Mandanten Administrators für den Microsoft 365-Mandanten an, der den Buchungskalender hostet, den Sie dauerhaft löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="87408-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="87408-125">Geben Sie an der PowerShell-Eingabeaufforderung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="87408-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="87408-126">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="87408-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="87408-127">Sobald dieser Befehl verarbeitet wurde, geben Sie den folgenden Befehl ein, um eine Liste der Buchungspostfächer in Ihrem Mandanten abzurufen:</span><span class="sxs-lookup"><span data-stu-id="87408-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="87408-128">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="87408-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="87408-129">Achten Sie darauf, den genauen Namen des Buchungs Post Fach Alias einzugeben, den Sie dauerhaft löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="87408-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="87408-130">Um zu überprüfen, ob der Kalender gelöscht wurde, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="87408-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="87408-131">Der gelöschte Kalender wird in der Ausgabe nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="87408-131">The deleted calendar will not appear in the output.</span></span>
