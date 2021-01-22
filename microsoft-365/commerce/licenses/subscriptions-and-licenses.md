---
title: Informationen zu Abonnements und Lizenzen in Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Erfahren Sie mehr über Abonnements und Lizenzen in Microsoft 365 Business.
ms.date: 07/01/2020
ms.openlocfilehash: ccfcb52548fb79267c550afba63c2f5a96b99ed1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928510"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Informationen zu Abonnements und Lizenzen in Microsoft 365 Business

Wenn Sie ein Abonnement für Microsoft 365 Business erwerben, registrieren Sie sich für eine Reihe von Apps und Diensten, die Sie monatlich oder jährlich bezahlen. Welche Anwendungen und Dienste Sie als Teil Ihres Abonnements erhalten, hängt davon ab, welches Produkt Sie erworben haben, z. B. Microsoft 365 Apps for Business oder Microsoft 365 Business Standard. Auf der Seite ["Microsoft 365](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1) für kleine und mittelständische Unternehmen" können Sie sehen, was die einzelnen Produkte mit sich bringt.

Wenn Sie ein Abonnement kaufen, geben Sie die Anzahl der Lizenzen an, die Sie benötigen, und zwar basierend auf der Anzahl der in Ihrer Organisation beschäftigten Mitarbeiter. Nachdem Sie ein Abonnement gekauft haben, erstellen Sie Konten für Personen in Ihrer Organisation und weisen jeder Person eine Lizenz zu. Wenn sich die Anforderungen Ihrer Organisation ändern, können Sie zusätzliche Lizenzen für neue Benutzer erwerben, oder bestehende Lizenzen anderen Benutzern zuweisen, wenn jemand Ihre Organisation verlässt.

Wenn Sie über mehr als ein Abonnement verfügen, können Sie unterschiedlichen Personen Lizenzen aus dem jeweiligen Abonnement zuweisen. Sie können beispielsweise alle Ihre Benutzer allen Microsoft 365-Anwendungen und -Diensten im Rahmen eines Microsoft 365 Business Standard-Abonnements zuweisen. Sie können Visio Online auch eine Teilmenge von Benutzern über ein separates Abonnement von Visio zuweisen.

## <a name="how-many-devices-can-people-install-office-on"></a>Auf wie vielen Geräten kann Office installiert werden?

Wenn Ihr Abonnement eines der folgenden Produkte umfasst, kann jede Person Office auf bis zu fünf PCs oder Macs, fünf Tablets und fünf Smartphones installieren.

:::row:::
   :::column span="":::
        - Microsoft 365 Apps for Business - Microsoft 365 Apps for Enterprise - Microsoft 365 Business Standard - Microsoft 365 Business Premium - Microsoft 365 A3 - Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 - Microsoft 365 E5 - Office 365 A1 Plus - Office 365 A3 - Office 365 A5 - Office 365 E3 - Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>Was geschieht, wenn Sie einer Person eine Lizenz zuweisen?

In der folgenden Tabelle wird aufgeführt, was automatisch passiert, wenn Sie einem Benutzer eine Lizenz zuweisen:
  
|**Bei diesem Dienst zum Abonnement**|**Dies geschieht automatisch**|
|:-----|:-----|
|Exchange Online  <br/> |Es wird ein Postfach für diese Person erstellt. <br/> Informationen zum SLA für diesen Vorgang finden Sie unter ["Einrichten..." nachrichten im Microsoft 365 Admin Center .](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center) |
|SharePoint Online  <br/> |Dieser Person werden Bearbeitungsberechtigungen für die standardmäßige SharePoint Online-Teamwebsite zugewiesen.  <br/> |
|Skype for Business Online  <br/> |Die Person hat Zugriff auf die Features, die der Lizenz zugeordnet sind.  <br/> |
|Microsoft 365 Apps for Enterprise  <br/> |Die Person kann die Office-Apps auf bis zu fünf Macs oder PCs, fünf Tablets und fünf Smartphones herunterladen.  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>Grundlegendes zu Lizenzen für nicht benutzergebundene Postfächer

Sie müssen keine Lizenzen für Ressourcenpostfächer, Raumpostfächer und freigegebene Postfächer zuweisen, es sei denn, das Speicherkontingent von 50 Gigabyte (GB) wird überschritten. Weitere Informationen zu nicht benutzergebundenen Postfächern finden Sie in den folgenden Artikeln:
  
- [Erstellen eines freigegebenen Postfachs](../../admin/email/create-a-shared-mailbox.md)
- [Entfernen einer Lizenz aus einem freigegebenen Postfach](../../admin/email/remove-license-from-shared-mailbox.md)
- [Freigegebene Postfächer in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes) für alle anderen Microsoft 365-Pläne.
- [Erstellen und Verwalten von Raumpostfächern](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [Verwalten von Gerätepostfächern](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>Wer kann Lizenzen zuweisen?

Verschiedene Typen von Administratoren können je nach den ihnen zugewiesenen Rollen auf unterschiedliche Weise mit Lizenzen arbeiten. In der folgenden Tabelle finden Sie eine Liste der häufigsten Optionen. Eine vollständige Liste der Administratorrollen und -berechtigungen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  
|**Administratorrolle**|**Lizenz zuweisen**|**Unassign a license**|**Erwerben von weiteren Lizenzen**|**Löschen eines Kontos**|
|:-----|:-----|:-----|:-----|:-----|
|Rechnungsadministrator  <br/> |Nein  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |
|Globaler Administrator  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Lizenzadministrator <br/> |Ja <br/>|Ja <br/> |Nein <br/> |Nein <br/> |
|Dienstsupportadministrator  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Benutzeradministrator  <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |Ja  <br/> |

## <a name="related-content"></a>Verwandte Inhalte

[Kaufen oder Entfernen von Lizenzen für Ihr Geschäftsabonnement](buy-licenses.md) (Artikel)\
[Zuweisen von Lizenzen zu Benutzern ](../../admin/manage/assign-licenses-to-users.md) (Artikel)\
[Aufheben der Zuweisung von Benutzerlizenzen](../../admin/manage/remove-licenses-from-users.md) (Artikel)\
[Entfernen einer Lizenz aus einem freigegebenen Postfach](../../admin/email/remove-license-from-shared-mailbox.md) (Artikel)