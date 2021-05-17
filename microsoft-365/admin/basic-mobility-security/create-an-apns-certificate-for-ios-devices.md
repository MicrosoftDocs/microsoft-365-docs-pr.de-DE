---
title: Erstellen eines APNs-Zertifikats für iOS-Geräte
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
description: Verwalten von iOS-Geräten in Basic Mobility and Security.
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877080"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="16cff-103">Erstellen eines APNs-Zertifikats für iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="16cff-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="16cff-104">Erstellen Sie ein APNs-Zertifikat, um iOS-Geräte wie iPads und iPhones in Basic Mobility and Security zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="16cff-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="16cff-105">Melden Sie sich bei Microsoft 365 mit Ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="16cff-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="16cff-106">Geben Sie in Ihrem Browser  [https://protection.office.com](https://protection.office.com/) ein.</span><span class="sxs-lookup"><span data-stu-id="16cff-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="16cff-107">Wählen  **Sie Verhinderung von Datenverlust**   >  **Geräteverwaltung** aus, und wählen Sie **APNs-Zertifikat für iOS-Geräte aus.**</span><span class="sxs-lookup"><span data-stu-id="16cff-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="16cff-108">Wählen Sie auf der Seite Apple Push Notification Certificate Einstellungen Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="16cff-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="16cff-109">Wählen Sie Csr-Datei herunterladen aus, und speichern Sie die Zertifikatsignieranforderung an einem Ort auf Ihrem Computer, an den Sie sich erinnern werden.</span><span class="sxs-lookup"><span data-stu-id="16cff-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="16cff-110">Wählen Sie  **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="16cff-110">Select  **Next**.</span></span>

6. <span data-ttu-id="16cff-111">Auf der Seite ApNs-Zertifikat erstellen:</span><span class="sxs-lookup"><span data-stu-id="16cff-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="16cff-112">Wählen Sie Apple APNS Portal aus, um das Apple Push Certificates Portal zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="16cff-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="16cff-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="16cff-113">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="16cff-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="16cff-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="16cff-116">Wählen  **Sie Zertifikat erstellen aus,** und akzeptieren Sie die   Nutzungsbedingungen.</span><span class="sxs-lookup"><span data-stu-id="16cff-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="16cff-117">Navigieren Sie zu der Zertifikatsignaturanforderung, die Sie auf Ihren Computer heruntergeladen haben, Microsoft 365, und wählen Sie **Hochladen** aus.</span><span class="sxs-lookup"><span data-stu-id="16cff-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

        <span data-ttu-id="16cff-118">Laden Sie das vom Apple Push Certificate Portal erstellte APNs-Zertifikat auf Ihren Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="16cff-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       >[!TIP]
       ><span data-ttu-id="16cff-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="16cff-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="16cff-120">Wechseln Sie zurück zu Microsoft 365, und wählen Sie **Weiter** aus, um zur Seite   Hochladen   **APNS-Zertifikats zu**   gelangen.</span><span class="sxs-lookup"><span data-stu-id="16cff-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="16cff-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="16cff-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="16cff-122">Wählen Sie  **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="16cff-122">Select  **Finish**.</span></span>

<span data-ttu-id="16cff-123">Um das Setup abzuschließen, wechseln Sie zurück zum Security  \*\*\*\*& Compliance Center >  >  **Sicherheitsrichtlinien Geräteverwaltung**   >  **Verwalten von Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="16cff-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
