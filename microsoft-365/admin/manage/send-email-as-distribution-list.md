---
title: Senden von E-Mails als Verteilerliste
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
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Senden Sie E-Mails als Verteilerliste in Microsoft 365, sodass ein Mitglied auf eine Nachricht antwortet, die aus der Verteilerliste stammt.
ms.openlocfilehash: c77455b5b990a9c35fc7e47ee81cc9ddef4d0a23
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392515"
---
# <a name="send-email-as-a-distribution-list"></a>Senden von E-Mails als Verteilerliste

In Microsoft 365 können Sie E-Mails als Verteilerliste senden. Wenn eine Person, die Mitglied der Verteilerliste ist, auf eine an die Verteilerliste gesendete Nachricht antwortet, sieht es so aus, als ob die E-Mail von der Verteilerliste und nicht vom einzelnen Benutzer stammt. In diesem Thema wird gezeigt, wie das geht.
  
## <a name="before-you-begin"></a>Bevor Sie beginnen:

Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie einer Microsoft 365 Verteilerliste hinzugefügt wurden und Ihnen die Berechtigung "Senden als" gewährt wurde.
  
 **Administratoren:** Stellen Sie sicher, dass Sie die Schritte unter ["Hinzufügen eines Microsoft 365 Benutzers oder Kontakts zu einer Liste"](../email/add-user-or-contact-to-distribution-list.md) befolgt haben und Mitgliedern das Senden von [E-Mails als Microsoft 365 Gruppenthemen erlauben,](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) und die richtigen Personen zur Verteilerliste hinzugefügt haben.
  
## <a name="outlook-on-the-web"></a>Outlook im Web

1. Öffnen Sie Outlook im Web, und wechseln Sie zu Ihrem Posteingang. 
    
2. Öffnen Sie eine an die Verteilerliste gesendete Nachricht. 
    
3. Wählen Sie **"Antworten" aus.** 
    
4. Wählen Sie unten in der Nachricht **weitere** \> **Anzeigen aus.**<br/> ![Wählen Sie "Mehr" und dann "Aus anzeigen" aus.](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)
  
5. Klicken Sie mit der rechten Maustaste auf die Absenderadresse , z. B. `Ina@weewalter.me` und wählen Sie **"Entfernen"** aus.<br/> ![Entfernen des FROM-Alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)
  
6. Geben Sie dann die Verteilerlistenadresse ein, z. B. support@contoso.com, und senden Sie die Nachricht. Wenn Sie das nächste Mal aus der Verteilerliste antworten, wird die Adresse als Option in der **Von-Liste** angezeigt.<br/>![Alias des freigegebenen Postfachs wird angezeigt](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)

## <a name="outlook"></a>Outlook

1. Öffnen Sie Outlook Desktopclient.

2. Verfassen sie eine neue E-Mail. Klicken Sie auf das **Feld "Von",** und wählen Sie **"Andere E-Mail-Adresse"** aus. Wenn das Feld "Von" nicht angezeigt wird, navigieren Sie zu **"Optionen",** und wählen Sie im Abschnitt "Felder anzeigen" die Option **"Von" aus.**

3. Wählen Sie die Adresse der **Verteilerliste** aus der globalen Adressliste aus.

4. Senden Sie die E-Mail.

## <a name="related-content"></a>Verwandte Inhalte

[Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center](../email/create-edit-or-delete-a-security-group.md) (Artikel)\
[E-Mail-Zusammenarbeit](../email/email-collaboration.md) (Artikel)\
[Hinzufügen eines Benutzers oder Kontakts zu einer Verteilergruppe](../email/add-user-or-contact-to-distribution-list.md) (Artikel)