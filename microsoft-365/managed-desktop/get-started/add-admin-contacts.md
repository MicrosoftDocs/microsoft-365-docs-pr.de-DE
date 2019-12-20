---
title: Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal
description: Teilen Sie uns mit, an wen Sie sich für jeden Bereich des Fokus wenden müssen.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: d34d7082150b4131634fb695ce6664ded50e6f9d
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823837"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal

Es gibt mehrere Möglichkeiten, wie Microsoft Managed Desktop Service mit Kunden kommuniziert. Um die Kommunikation zu rationalisieren und sicherzustellen, dass die richtigen Personen überprüft werden, müssen Sie eine Reihe von Administrator Kontakten bereitstellen. Microsoft Managed Desktop-IT-Vorgänge wenden sich an diese Personen, um Hilfe bei der Problembehandlung für Ihren Mandanten zu erhalten.

> [!IMPORTANT]
> Möglicherweise haben Sie diese Kontakte bereits im Administratorportal hinzugefügt. Wenn dies der Fall ist, überprüfen Sie jetzt, ob die Kontaktliste korrekt ist, da Microsoft Managed Desktop Sie bei einem schweren Vorfall **erreichen kann.**

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory Access für das Verwaltungsportal von Microsoft Managed Desktop

Microsoft Managed Desktop Admin Portal erfordert, dass Personen, die auf das Portal zugreifen, über eine dieser Azure Active Directory (AD)-Rollen verfügen:
- Globaler Administrator
- InTune-Dienst Administrator
- Abrechnungs Administrator
- Dienst Support Administrator

Der globale Administrator muss der einzige sein, der Ihre Organisation in Microsoft Managed Desktop registriert. Alle fünf Rollen haben im Administratorportal denselben Zugriff, um Aufgaben zu initiieren und anzuzeigen. Weitere Informationen zum Zuweisen dieser Rollen in Azure AD finden Sie unter [Administrator Role Permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). 

## <a name="admin-contact-areas-of-focus"></a>Administrative Kontaktbereiche des Fokus

Administrator Kontakte sollten die beste Person oder Gruppe sein, die Fragen beantworten und Entscheidungen für unterschiedliche Fokusbereiche treffen kann. **Bei Microsoft Managed Desktop Operations werden diese Administrator Kontakte für Fragen im Zusammenhang mit Supportanfragen, die vom Kunden eingereicht wurden, kontaktiert.** Diese Administrator Kontakte erhalten Benachrichtigungen für Updates für Supportanfragen und neue Nachrichten. Diese Bereiche umfassen:

Fokusbereich | Fragen zu
--- | ---
App-Verpackung | Problembehandlung bei App-Verpackungen
Geräte | Geräte Integrität, Problembehandlung mit Microsoft Managed Desktop-Geräten
Sicherheit | Beheben von Sicherheitsproblemen mit Microsoft Managed Desktop-Geräten
IT-Helpdesk | in Fällen, in denen unser Supportmitarbeiter Karten für Endbenutzer außerhalb der Microsoft Managed Desktop-Support Bereiche übergibt 
Andere | Für Probleme, die nicht von anderen Bereichen abgedeckt werden

**Wer auch immer Sie für diese Kontakte ausgewählt haben, muss über das Wissen und die Autorität verfügen, um Entscheidungen für Ihre von Microsoft verwaltete Desktop Umgebung zu treffen.** Wenn Sie Ihre Microsoft Managed Desktop-Umgebung an Bord haben, werden Sie aufgefordert, Kontakte für den lokalen Helpdesk und die Sicherheit hinzuzufügen. 

Administrator Kontakte sind erforderlich, wenn Sie [eine Support Anfrage übermitteln](../service-description/support.md). Sie benötigen einen Administratorkontakt für den Fokusbereich der Support Anfrage. 

**So fügen Sie Administrator Kontakte hinzu**

1.  Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mwaasportal)an. 

2.  Wählen Sie unter **Support**die Option **Administrator Kontakte**aus. 

    ![Support-Menü, Administrator Kontakte in der Nähe der oben ausgewählten](images/admincontacts.png)

3. Klicken Sie auf **Hinzufügen**.

    ![Verwaltungsportal, Schaltfläche hinzufügen, Links von Export und Aktualisierung](images/adminadd.png)

4.  Wählen Sie einen **Fokusbereich** aus, und geben Sie die Informationen für den Kontakt ein. 

    ![die Liste der Fokusbereiche, beispielsweise andere, Apps und Sicherheit](images/areaoffocus.png)

5. Wiederholen Sie diese Schritte für jeden Bereich des Fokus. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Schritte zum Einstieg in Microsoft Managed Desktop

1. Hinzufügen und Überprüfen von Administrator Kontakten im Administratorportal (in diesem Thema)
2. [Bedingten Zugriff anpassen](conditional-access.md)
3. [Zuweisen von Lizenzen](assign-licenses.md)
4. [Installieren des InTune-Unternehmensportals auf auf Geräten](company-portal.md)
5. [Aktivieren von Enterprise State Roaming](enterprise-state-roaming.md)
6. [Einrichten von Microsoft Managed Desktop-Geräten](set-up-devices.md)
7. [Vorbereiten Ihrer Benutzer für die Verwendung von Geräten](get-started-devices.md)
8. [Bereitstellen von apps auf Geräten](deploy-apps.md)