---
title: Freigeben von Kalendern für externe Benutzer
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
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 'Erfahren Sie, wie Sie Ihren Benutzern die Freigabe Ihrer Kalender mit externen Benutzern für Besprechungen und Termine ermöglichen können. '
ms.openlocfilehash: 972e8376ae3d71b11205d4a6611dc6900c063ffe
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780061"
---
# <a name="share-calendars-with-external-users"></a>Freigeben von Kalendern für externe Benutzer

[] Es ist oft notwendig, Besprechungen mit Personen außerhalb Ihrer Organisation zu planen. Um den Prozess der Suche nach gegenseitig annehmbaren Besprechungszeiten zu vereinfachen, ermöglicht Ihnen Microsoft 365 das Bereitstellen von Kalendern für "externe Benutzer", die Frei/Gebucht-Zeiten anzeigen müssen, aber keine Benutzerkonten für Ihre Microsoft 365-Umgebung haben.
  
Die Kalenderfreigabe ist eine globale Einstellung, was bedeutet, dass Sie Sie als Administrator für alle Benutzer im Mandanten aktivieren können. Nachdem die Freigabe aktiviert wurde, können Benutzer Outlook Web App verwenden, um ihre Kalender mit beliebigen Personen innerhalb oder außerhalb der Organisation zu teilen. Personen innerhalb der Organisation können freigegebene Kalender neben ihren eigenen anzeigen. An Personen außerhalb der Organisation wird eine URL gesendet, über die sie den Kalender anzeigen können. Die Benutzer entscheiden, wann sie teilen möchten, wie viel sie teilen möchten und wann sie ihre Kalender privat halten möchten.
  
> [!NOTE]
> If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information. 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a>Aktivieren der Kalenderfreigabe mit dem Microsoft 365 Admin Center

1. Navigieren Sie im Admin Center zu **Einstellungen** \> **org Settings**. 
    
2. Wählen Sie auf der Registerkarte **Dienste** die Option **Kalender**aus.
  
3. Wählen Sie auf der daraufhin geöffneten **Kalender** Seite aus, ob Ihre Benutzer ihre Kalender für Personen außerhalb Ihrer Organisation freigeben möchten, die über Microsoft 365 oder Exchange verfügen.
    
4. Wählen Sie aus, ob Sie anonymen Benutzern (Benutzern ohne Anmeldeinformationen) den Zugriff auf Kalender über eine e-Mail-Einladung erlauben möchten.

5. Wählen Sie den Typ der Kalenderinformationen aus, die für Benutzer verfügbar gemacht werden sollen. Sie können alle Informationen zulassen oder nur auf Zeit, Zeit, Betreff und Ort beschränken.

    
## <a name="invite-people-to-access-calendars"></a>Personen zum Zugreifen auf Kalender einladen

Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions. 
  
