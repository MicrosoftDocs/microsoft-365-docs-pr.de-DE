---
title: Schritt 6 – Entfernen und Löschen Microsoft 365 Lizenz eines ehemaligen Mitarbeiters
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Führen Sie die folgenden Schritte aus, um die Microsoft 365 von einem ehemaligen Mitarbeiter zu entfernen.
ms.openlocfilehash: ed86eb28cc6d4996f7def8cb567f0e4085e67624
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244216"
---
# <a name="step-6---remove-the-microsoft-365-license-from-a-former-employee"></a>Schritt 6 – Entfernen Microsoft 365 Lizenz eines ehemaligen Mitarbeiters

Wenn Sie keine Lizenz bezahlen möchten, nachdem jemand Ihre Organisation verlässt, müssen Sie ihre Microsoft 365 lizenz entfernen und dann aus Ihrem Abonnement löschen. Sie können einem anderen Benutzer eine Lizenz zuweisen, wenn Sie sie nicht löschen.
  
Wenn Sie die Lizenz entfernen, werden alle Daten des Benutzers noch 30 Tage gespeichert. Sie können auf die Daten [zugreifen](get-access-to-and-back-up-a-former-user-s-data.md) oder das Konto [wiederherstellen](restore-user.md), wenn der Benutzer zurückkehrt. Nach 30 Tagen werden alle Benutzerdaten (mit Ausnahme von Dokumenten, die auf SharePoint Online gespeichert sind) endgültig aus Microsoft 365 gelöscht und können nicht wiederhergestellt werden.

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie den Namen des Mitarbeiters aus, den Sie blockieren möchten, und wählen Sie dann die Registerkarte **Lizenzen und Apps** aus.
3. Aktivieren Sie die Kontrollkästchen für die Lizenz(en), die Sie entfernen möchten, und wählen Sie **dann Änderungen speichern aus.**

**Gehen Sie wie folgt vor,** um die Anzahl der Lizenzen zu reduzieren, die Sie bezahlen, bis Sie eine andere Person einstellen:

1. Wechseln Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte,</a> und wählen Sie die Registerkarte **Produkte** aus.
2. Wählen Sie das Abonnement aus, aus dem Sie Lizenzen entfernen möchten.
3. Wählen Sie auf der Detailseite Lizenzen **entfernen aus.**
4. Geben Sie **im Bereich** Lizenzen entfernen  unter Neue Menge im Feld Lizenzen insgesamt die Gesamtzahl der Lizenzen ein, die Sie für dieses Abonnement benötigen. Wenn Sie beispielsweise über 25 Lizenzen verfügen und eine davon entfernen möchten, geben Sie 24 ein.
5. Klicken Sie auf **Speichern**.

Wenn Sie [Ihrem](add-users.md) Unternehmen eine andere Person hinzufügen, werden Sie aufgefordert, gleichzeitig eine Lizenz zu erwerben, und dies mit nur einem Schritt!

Weitere Informationen zum Verwalten von Benutzerlizenzen für Microsoft 365 business finden Sie unter Zuweisen von Lizenzen zu Benutzern [in Microsoft 365 for Business](../manage/assign-licenses-to-users.md)und Zuweisen von Lizenzen von Benutzern in Microsoft 365 [Business](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Auswirkungen des gelöschten Mitarbeiterkontos auf Skype for Business

Wenn Sie die Lizenz eines Benutzers aus Office 365 entfernen, wird die dem Benutzer zugeordnete PSTN Calling-Nummer freigegeben. Sie können sie dann einem anderen Benutzer zuweisen.
  
Wenn der Benutzer einer Warteschlangengruppe angehört, ist er kein erreichbares Ziel der Anrufwarteschlangen-Agents mehr. Deshalb empfiehlt es sich, den Benutzer auch aus den Gruppen zu entfernen, die der Anrufwarteschlange zugeordnet sind.

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>Einrichten der Anruf weiterleitung an Personen in Ihrer Organisation

Wenn Sie die Anrufzusende für die Telefonnummer des gekündigten Mitarbeiters einrichten müssen, kann die Anruf weiterleitungseinstellung unter Anrufrichtlinien die Weiterleitung einrichten, bei der eingehende Anrufe an andere Benutzer weitergeleitet werden können oder eine andere Person gleichzeitig anrufen kann. Weitere Informationen finden Sie unter [Aufrufen von Richtlinien in Microsoft Teams](/microsoftteams/teams-calling-policy).
