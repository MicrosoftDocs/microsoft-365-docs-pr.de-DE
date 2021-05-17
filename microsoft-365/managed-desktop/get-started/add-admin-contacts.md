---
title: Hinzufügen und Überprüfen von Administrator-Kontakten im Administratorportal
description: Teilen Sie uns mit, wer für jeden Fokusbereich kontaktiert werden soll.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925892"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Hinzufügen und Überprüfen von Administrator-Kontakten im Administratorportal

Es gibt verschiedene Möglichkeiten, Microsoft Managed Desktop Dienst mit Kunden kommuniziert. Um die Kommunikation zu optimieren und sicherzustellen, dass wir mit den richtigen Personen suchen, müssen Sie eine Reihe von Administratorkontakten bereitstellen. Microsoft Managed Desktop IT-Vorgänge wenden sich an diese Personen, um Unterstützung bei der Problembehandlung für Ihren Mandanten zu erhalten.

> [!IMPORTANT]
> Möglicherweise haben Sie diese Kontakte bereits im Administratorportal hinzugefügt. Wenn ja, nehmen Sie sich jetzt einen Moment Zeit, um zu  überprüfen, ob die Kontaktliste richtig ist, da Microsoft Managed Desktop in der Lage sein muss, sie zu erreichen, wenn ein schwerwiegender Vorfall auftritt.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory für Microsoft Managed Desktop Administratorportal

Microsoft Managed Desktop Das Administratorportal erfordert, dass Personen, die auf das Portal zugreifen, über eine der folgenden Azure Active Directory (AD) verfügen:
- Globaler Administrator
- Intune-Dienstadministrator
- Globaler Leser
- Dienstunterstützungsadministrator

Der globale Administrator muss der Benutzer sein, der Ihre Organisation bei der Microsoft Managed Desktop. Alle fünf Rollen verfügen über denselben Zugriff innerhalb des Administratorportals zum Initiieren und Anzeigen von Aufgaben. Weitere Informationen zum Zuweisen dieser Rollen in Azure AD finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). 

## <a name="admin-contact-areas-of-focus"></a>Fokusbereiche für Administratorkontakte

Administratorkontakte sollten die beste Person oder Gruppe sein, die Fragen beantworten und Entscheidungen für verschiedene Schwerpunktbereiche treffen kann. **Microsoft Managed Desktop Die Vorgänge wenden sich an diese Administratorkontakte für Fragen im Zusammenhang mit Supportanfragen, die vom Kunden gestellt wurden.** Diese Administratorkontakte erhalten Benachrichtigungen für Supportanforderungsupdates und neue Nachrichten. Zu diesen Bereichen gehören:

Fokusbereich | Für Fragen zu
--- | ---
App-Verpackung | Problembehandlung beim Packen von Apps
Geräte | Geräteinte health, Problembehandlung bei Microsoft Managed Desktop Geräten
Sicherheit | Problembehandlung bei Sicherheitsproblemen mit Microsoft Managed Desktop Geräten
IT-Helpdesk | in Fällen, in denen unsere Supportmitarbeiter Benutzertickets außerhalb der Microsoft Managed Desktop aushändigen 
Andere | Bei Problemen, die nicht von anderen Bereichen abgedeckt werden

**Wer auch immer Sie für diese Kontakte auswählen, muss über das Wissen und die Autorität verfügen, um Entscheidungen für Ihre Umgebung Microsoft Managed Desktop treffen.** Wenn Sie Ihre Microsoft Managed Desktop integrieren, werden Sie aufgefordert, Kontakte für Ihren lokalen Helpdesk und Die Sicherheit hinzuzufügen. 

Administratorkontakte sind erforderlich, wenn [Sie eine Supportanfrage übermitteln.](../service-description/support.md) Sie benötigen einen Administratorkontakt für den Fokusbereich der Supportanfrage. 

**So fügen Sie Administratorkontakte hinzu**

1.  Melden Sie sich bei [Microsoft Managed Desktop Administratorportal an.](https://aka.ms/mwaasportal) 

2.  Wählen **Sie unter Support** die Option **Administratorkontakte aus.** 

    ![Supportmenü, Administratorkontakte in der Nähe der oberen auswahl](../../media/admincontacts.png)

3. Wählen Sie **Hinzufügen**.

    ![Administratorportal, Schaltfläche Hinzufügen links von Export and Refresh](../../media/adminadd.png)

4.  Wählen Sie **einen Fokusbereich aus,** und geben Sie die Informationen für den Kontakt ein. 

    ![die Liste der Schwerpunktbereiche, z. B. Other, Apps und Sicherheit](../../media/areaoffocus.png)

5. Wiederholen Sie dies für jeden Fokusbereich. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Schritte zum Einstieg in Microsoft Managed Desktop

1. Hinzufügen und Überprüfen von Administratorkontakten im Administratorportal (in diesem Thema)
2. [Bedingten Zugriff anpassen](conditional-access.md)
3. [Zuweisen von Lizenzen](assign-licenses.md)
4. [Installieren des Intune Company Portals auf Geräten](company-portal.md)
5. [Aktivieren von Enterprise State Roaming](enterprise-state-roaming.md)
6. [Richten Sie Microsoft Managed Desktop-Geräte ein](set-up-devices.md)
7. [Vorbereiten Ihrer Benutzer für die Verwendung von Geräten](get-started-devices.md)
8. [Stellen Sie Anwendungen auf Geräten bereit](deploy-apps.md)