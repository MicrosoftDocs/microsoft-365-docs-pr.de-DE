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
# <a name="create-an-apns-certificate-for-ios-devices"></a>Erstellen eines APNs-Zertifikats für IOS-Geräte

Um IOS-Geräte wie iPads und iPhones in grundlegender Mobilität und Sicherheit zu verwalten, erstellen Sie ein APNs-Zertifikat.

1. Melden Sie sich bei Microsoft 365 mit ihrem globalen Administratorkonto an.
    
2. Geben Sie in Ihrem Browser ein  [https://protection.office.com](https://protection.office.com/) .
    
3. Wählen Sie  **Data Loss Prevention**   >  **Device Management**aus, und wählen Sie **APNs-Zertifikat für IOS-Geräte**aus.    

4. Klicken Sie auf der Seite Einstellungen für den Apple Push Notification-Zertifikat auf **weiter**.
    
5. Wählen Sie Download your CSR File aus, und speichern Sie die Zertifikatsignaturanforderung an einer beliebigen Stelle auf Ihrem Computer, an der Sie sich erinnern. Wählen Sie  **weiter**aus.
    
6. Auf der Seite APNs-Zertifikat erstellen:  

    1. Wählen Sie Apple APNS Portal aus, um das Apple Push Certificates-Portal zu öffnen.
    
    2. Sign in with an Apple ID.   

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Wählen Sie  **Zertifikat erstellen** aus   , und akzeptieren Sie die Nutzungsbedingungen.
    
    4. Wechseln Sie zu der Zertifikatsignaturanforderung, die Sie von Microsoft 365 auf Ihren Computer heruntergeladen haben, und wählen Sie **hochladen**aus.
    
        Laden Sie das vom Apple Push Certificate-Portal erstellte APNs-Zertifikat auf Ihren Computer herunter.
    
       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. Wechseln Sie zurück zu Microsoft 365, und wählen Sie **weiter** ,   um zur Seite  **APNS-Zertifikat hochladen**zu gelangen   .
    
8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.
    
9. Wählen Sie  **Fertig stellen**aus.
    
Um das Setup abzuschließen, gehen Sie zurück zum Security & Compliance Center > **Sicherheitsrichtlinien**   >  **Geräteverwaltung**   >  **Einstellungen verwalten**.
