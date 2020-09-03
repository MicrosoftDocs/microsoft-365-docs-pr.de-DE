---
title: Erstellen eines APNs-Zertifikats für IOS-Geräte
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: Verwalten von IOS-Geräten in grundlegender Mobilität und Sicherheit.
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336909"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="58950-103">Erstellen eines APNs-Zertifikats für IOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="58950-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="58950-104">Um IOS-Geräte wie iPads und iPhones in grundlegender Mobilität und Sicherheit zu verwalten, erstellen Sie ein APNs-Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="58950-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="58950-105">Melden Sie sich bei Microsoft 365 mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="58950-105">Sign in to Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="58950-106">Geben Sie in Ihrem Browser ein  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="58950-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>
    
3. <span data-ttu-id="58950-107">Wählen Sie  **Data Loss Prevention**   >  **Device Management**aus, und wählen Sie **APNs-Zertifikat für IOS-Geräte**aus.</span><span class="sxs-lookup"><span data-stu-id="58950-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>    

4. <span data-ttu-id="58950-108">Klicken Sie auf der Seite Einstellungen für den Apple Push Notification-Zertifikat auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="58950-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>
    
5. <span data-ttu-id="58950-109">Wählen Sie Download your CSR File aus, und speichern Sie die Zertifikatsignaturanforderung an einer beliebigen Stelle auf Ihrem Computer, an der Sie sich erinnern.</span><span class="sxs-lookup"><span data-stu-id="58950-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="58950-110">Wählen Sie  **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="58950-110">Select  **Next**.</span></span>
    
6. <span data-ttu-id="58950-111">Auf der Seite APNs-Zertifikat erstellen:</span><span class="sxs-lookup"><span data-stu-id="58950-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="58950-112">Wählen Sie Apple APNS Portal aus, um das Apple Push Certificates-Portal zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="58950-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
    
    2. <span data-ttu-id="58950-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="58950-113">Sign in with an Apple ID.</span></span>   

    >[!IMPORTANT]
    ><span data-ttu-id="58950-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="58950-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="58950-116">Wählen Sie  **Zertifikat erstellen** aus   , und akzeptieren Sie die Nutzungsbedingungen.</span><span class="sxs-lookup"><span data-stu-id="58950-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>
    
    4. <span data-ttu-id="58950-117">Wechseln Sie zu der Zertifikatsignaturanforderung, die Sie von Microsoft 365 auf Ihren Computer heruntergeladen haben, und wählen Sie **hochladen**aus.</span><span class="sxs-lookup"><span data-stu-id="58950-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>
    
        <span data-ttu-id="58950-118">Laden Sie das vom Apple Push Certificate-Portal erstellte APNs-Zertifikat auf Ihren Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="58950-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>
    
       >[!TIP]
       ><span data-ttu-id="58950-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="58950-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="58950-120">Wechseln Sie zurück zu Microsoft 365, und wählen Sie **weiter** ,   um zur Seite  **APNS-Zertifikat hochladen**zu gelangen   .</span><span class="sxs-lookup"><span data-stu-id="58950-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>
    
8. <span data-ttu-id="58950-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="58950-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
9. <span data-ttu-id="58950-122">Wählen Sie  **Fertig stellen**aus.</span><span class="sxs-lookup"><span data-stu-id="58950-122">Select  **Finish**.</span></span>
    
<span data-ttu-id="58950-123">Um das Setup abzuschließen, gehen Sie zurück zum Security & Compliance Center > **Sicherheitsrichtlinien**   >  **Geräteverwaltung**   >  **Einstellungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="58950-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
