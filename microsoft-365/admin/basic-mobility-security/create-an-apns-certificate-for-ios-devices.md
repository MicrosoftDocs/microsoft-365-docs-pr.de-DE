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
ms.openlocfilehash: 84f3589593ef26325397f5b6e90d5b21662d2352
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228243"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Erstellen eines APNs-Zertifikats für iOS-Geräte

Um iOS-Geräte wie iPads und iPhones in Basic Mobility and Security zu verwalten, erstellen Sie ein APNs-Zertifikat.

1. Melden Sie sich mit Ihrem globalen Administratorkonto bei Microsoft 365 an.

2. Geben Sie in Ihrem Browser  <https://protection.office.com/> .

3. Wählen Sie  **"Geräteverwaltung zur Verhinderung von Datenverlust"**   >  **** und dann **"APNs-Zertifikat" für iOS-Geräte** aus.

4. Wählen Sie auf der Seite "Apple Push Notification Certificate Einstellungen" die Option **"Weiter"** aus.

5. Wählen Sie "CSR-Datei herunterladen" aus, und speichern Sie die Zertifikatsignierungsanforderung an einer Stelle auf Ihrem Computer, an die Sie sich erinnern werden. Wählen Sie  **"Weiter"** aus.

6. Auf der Seite zum Erstellen eines APNs-Zertifikats:

    1. Wählen Sie das Apple APNS-Portal aus, um das Apple Push Certificates Portal zu öffnen.

    2. Sign in with an Apple ID.

       > [!IMPORTANT]
       > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Wählen Sie  **"Zertifikat erstellen"**   aus, und akzeptieren Sie die Nutzungsbedingungen.

    4. Navigieren Sie zu der Zertifikatsignierungsanforderung, die Sie von Microsoft 365 auf Ihren Computer heruntergeladen haben, und wählen Sie **Hochladen** aus.

       Laden Sie das vom Apple Push Certificate Portal erstellte APNs-Zertifikat auf Ihren Computer herunter.

       > [!TIP]
       > If you're having trouble downloading the certificate, refresh your browser.

7. Wechseln Sie zurück zu Microsoft 365, und wählen Sie **"Weiter"**   aus, um zur   **APNS-Zertifikatseite Hochladen** zu   gelangen.

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Wählen Sie  **"Fertig stellen"** aus.

Um die Einrichtung abzuschließen, wechseln Sie zurück zum Security & Compliance Center > **Sicherheitsrichtlinien**   >  **Geräteverwaltung**   >  **– Verwalten von Einstellungen.**
