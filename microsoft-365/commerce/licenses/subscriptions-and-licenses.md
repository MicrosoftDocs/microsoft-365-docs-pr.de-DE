---
title: Grundlegendes zu Abonnements und Lizenzen in Microsoft 365 for Business
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Erfahren Sie mehr über Abonnements und Lizenzen in Microsoft 365 for Business.
ms.date: 07/01/2020
ms.openlocfilehash: 9f8576b00b942c4b38d6192770bd2128afb4b104
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015959"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Grundlegendes zu Abonnements und Lizenzen in Microsoft 365 for Business

Wenn Sie ein Abonnement für Microsoft 365 for Business erwerben, registrieren Sie sich für eine Reihe von apps und Diensten, die Sie entweder monatlich oder jährlich bezahlen. Die Anwendungen und Dienste, die Sie im Rahmen Ihres Abonnements erhalten, hängen davon ab, welches Produkt Sie erworben haben, beispielsweise Microsoft 365 apps for Business oder Microsoft 365 Business Standard. Sie können sehen, was mit jedem Produkt auf der Seite [Microsoft 365 für kleine und mittelständische Unternehmen](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1) geliefert wird.

Wenn Sie ein Abonnement kaufen, geben Sie die Anzahl der Lizenzen an, die Sie benötigen, und zwar basierend auf der Anzahl der in Ihrer Organisation beschäftigten Mitarbeiter. Nachdem Sie ein Abonnement erworben haben, erstellen Sie Konten für Personen in Ihrer Organisation und weisen dann jeder Person eine Lizenz zu. Wenn sich die Anforderungen Ihrer Organisation ändern, können Sie zusätzliche Lizenzen für neue Benutzer erwerben, oder bestehende Lizenzen anderen Benutzern zuweisen, wenn jemand Ihre Organisation verlässt.

Wenn Sie über mehr als ein Abonnement verfügen, können Sie unterschiedlichen Personen Lizenzen aus dem jeweiligen Abonnement zuweisen. Beispielsweise können Sie alle Ihre Benutzer allen Microsoft 365-Anwendungen und-Diensten als Teil eines Microsoft 365 Business Standard-Abonnements zuweisen. Sie können Visio Online auch eine Teilmenge von Benutzern über ein separates Visio-Abonnement zuweisen.

## <a name="how-many-devices-can-people-install-office-on"></a>Auf wie vielen Geräten kann Office installiert werden?

Wenn Ihr Abonnement eines der folgenden Produkte enthält, kann jede Person Office auf bis zu fünf PCs oder Mac, fünf Tablets und fünf Telefonen installieren.

:::row:::
   :::column span="":::
        -Microsoft 365 apps for Business-Microsoft 365 apps for Enterprise-Microsoft 365 Business Standard-Microsoft 365 Business Premium-Microsoft 365 a3-Microsoft 365 a5
   :::column-end:::
   :::column span="":::
        -Microsoft 365 E3-Microsoft 365 E5-Office 365 a1 Plus-Office 365 a3-Office 365 A5-Office 365 E3-Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>Was geschieht, wenn Sie einer Person eine Lizenz zuweisen?

In der folgenden Tabelle wird aufgeführt, was automatisch passiert, wenn Sie einem Benutzer eine Lizenz zuweisen:
  
|**Bei diesem Dienst zum Abonnement**|**Dies geschieht automatisch**|
|:-----|:-----|
|Exchange Online  <br/> |Es wird ein Postfach für diese Person erstellt. <br/> Informationen zur SLA für diese Aufgabe, die abgeschlossen werden soll, finden Sie unter ["einrichten...". Nachrichten im Microsoft 365 Admin Center](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center). |
|SharePoint Online  <br/> |Dieser Person werden Bearbeitungsberechtigungen für die standardmäßige SharePoint Online-Teamwebsite zugewiesen.  <br/> |
|Skype for Business Online  <br/> |Die Person hat Zugriff auf die Funktionen, die der Lizenz zugeordnet sind.  <br/> |
|Microsoft 365 Apps for Enterprise  <br/> |Die Person kann Office-Apps auf bis zu fünf Macs oder PCs, fünf Tablets und fünf Smartphones herunterladen.  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>Grundlegendes zu Lizenzen für nicht benutzergebundene Postfächer

You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:
  
- [Erstellen eines freigegebenen Postfachs](../../admin/email/create-a-shared-mailbox.md)
- [Entfernen einer Lizenz aus einem freigegebenen Postfach](../../admin/email/remove-license-from-shared-mailbox.md)
- [Freigegebene Postfächer in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes) für alle anderen Microsoft 365-Pläne.
- [Erstellen und Verwalten von Raumpostfächern](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [Verwalten von Gerätepostfächern](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>Wer kann Lizenzen zuweisen?

Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  
|**Administratorrolle**|**Lizenz zuweisen**|**Aufheben der Zuweisung einer Lizenz**|**Erwerben weiterer Lizenzen**|**Löschen eines Kontos**|
|:-----|:-----|:-----|:-----|:-----|
|Rechnungsadministrator  <br/> |Nein  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |
|Globaler Administrator  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Lizenzadministrator <br/> |Ja <br/>|Ja <br/> |Nein <br/> |Nein <br/> |
|Dienst Support-Administrator  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Benutzeradministrator  <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |Ja  <br/> |

## <a name="related-content"></a>Verwandte Inhalte

[Erwerben oder Entfernen von Lizenzen für Ihr Geschäfts Abonnement](buy-licenses.md) (Artikel) \
[Zuweisen von Lizenzen zu Benutzern](../../admin/manage/assign-licenses-to-users.md) (Artikel) \
Aufheben [der Zuweisung von Lizenzen von Benutzern](../../admin/manage/remove-licenses-from-users.md) (Artikel) \
[Entfernen einer Lizenz aus einem freigegebenen Postfach](../../admin/email/remove-license-from-shared-mailbox.md) (Artikel)