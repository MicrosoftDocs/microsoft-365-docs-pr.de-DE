---
title: Hinzufügen von Administrator Kontakten im Microsoft Managed Desktop Admin Portal
description: Teilen Sie uns mit, wer für jeden Fokusbereich kontaktiert werden soll.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 014404ab38ff5871289be186dec150115c3be6ec
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277538"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a>Hinzufügen von Administrator Kontakten im Microsoft Managed Desktop Admin Portal

Es gibt mehrere Möglichkeiten, wie Microsoft Managed Desktop Service mit Kunden kommuniziert. Um die Kommunikation zu rationalisieren und sicherzustellen, dass wir die besten Kontakte überprüfen, müssen Sie eine Reihe von Administrator Kontakten bereitstellen. Microsoft Managed Desktop IT-Vorgänge wenden sich an diese Personen, um Hilfe bei der Problembehandlung für Ihren Mandanten zu erhalten. 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory-Zugriff für Microsoft Managed Desktop-Verwaltungsportal

Microsoft Managed Desktop Admin Portal erfordert, dass Personen, die auf das Portal zugreifen, über eine dieser Azure Active Directory-Rollen (AD) verfügen:
- Globaler Administrator
- InTune-Dienst Administrator
- Rechnungs Administrator
- Dienst Administrator

Der globale Administrator muss derjenige sein, der den Kunden in Microsoft Managed Desktop registriert.  Alle fünf Rollen haben den gleichen Zugriff innerhalb des Verwaltungsportals, um Aufgaben zu initiieren und anzuzeigen.  Weitere Informationen zum Zuweisen dieser Rollen in Azure AD finden Sie unter [Administrator Role Permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). 

## <a name="admin-contact-focus-areas"></a>Fokusbereiche für den admin-Kontakt

Administrator Kontakte sollten die beste Person oder Gruppe sein, die Fragen beantworten und Entscheidungen für unterschiedliche Fokusbereiche treffen kann.  Microsoft Managed Desktop Operations wendet sich an diese Administrator Kontakte für Fragen im Zusammenhang mit Supportanfragen des Kunden.  Diese Administrator Kontakte erhalten Benachrichtigungen für Updates für Supportanfragen und neue Nachrichten.  Hierzu gehört Folgendes:

Fokusbereich | Fragen zu
--- | ---
Apps | Problembehandlung bei App-Verpackungen
Geräte | Geräte Integrität, Problembehandlung mit Microsoft Managed Desktop-Geräten
Sicherheit | Behandeln von Sicherheitsproblemen mit Microsoft Managed Desktop-Geräten
Andere | Für Probleme, die nicht durch andere Bereiche abgedeckt werden

Wer immer Sie für diese Kontakte auswählen, muss über das Wissen und die Autorität verfügen, um Entscheidungen für Ihre Microsoft Managed Desktop-Umgebung treffen zu können. Wenn Sie Ihre Microsoft Managed Desktop-Umgebung Onboarding, werden Sie aufgefordert, Kontakte für Ihren lokalen Helpdesk und die Sicherheit hinzuzufügen. 

Administrator Kontakte sind erforderlich, wenn Sie [eine Support Anfrage übermitteln](../working-with-managed-desktop/support.md). Sie benötigen einen Administratorkontakt für den Fokusbereich der Support Anfrage. 

**So fügen Sie Administrator Kontakte hinzu**

1.  Melden Sie sich beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)an. 

2.  Wählen Sie unter **Support**die Option **Administrator Kontakte**aus. 

    ![Support Menü, Administrator Kontakte](images/admincontacts.png)

3. Klicken Sie auf **Hinzufügen**.

    ![Schaltfläche "Admin Portal hinzufügen"](images/adminadd.png)

4.  Wählen Sie einen **Fokusbereich** aus, und geben Sie die Informationen für den Kontakt ein. 

    ![die Liste der Fokusbereiche](images/areaoffocus.png)

5. Wiederholen Sie diese Schritte für jeden Fokusbereich. 

