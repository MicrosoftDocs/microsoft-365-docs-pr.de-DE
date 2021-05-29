---
title: Beheben von Problemen mit freigegebenen Postfächern
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Beim Einrichten freigegebener Postfächer können Fehler auftreten. Probieren Sie diese Lösungen aus, wenn Probleme mit freigegebenen Postfächern auftreten.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706130"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Beheben von Problemen mit freigegebenen Postfächern

Wenn beim Erstellen oder Verwenden eines freigegebenen Postfachs Fehlermeldungen angezeigt werden, versuchen Sie diese möglichen Lösungen. 

## <a name="error-when-creating-shared-mailboxes"></a>Fehler beim Erstellen freigegebener Postfächer
<a name="bkmk_Fix"> </a>

Wenn die Fehlermeldung angezeigt wird, wird die Proxyadresse "smtp:<freigegebener Postfachname" bereits von den Proxyadressen oder **\> LegacyExchangeDN von " \<name> verwendet. Wählen Sie eine andere Proxyadresse** aus, d. h. Sie versuchen, dem freigegebenen Postfach einen Namen zu geben, der bereits verwendet wird. Beispiel: Sie möchten freigegebenen Postfächern die Namen "info@domaene1" und "info@domaene2" geben. Sie können auf zwei Arten vorgehen:

  - Verwenden Sie Windows PowerShell. Anweisungen zum Erstellen freigegebener Postfächer mit demselben Alias in verschiedenen Domänen finden Sie in diesem [Blogbeitrag.](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Nennen Sie das zweite freigegebene Postfach etwas anders als am Anfang, um den Fehler zu beheben. Benennen Sie dann im Admin Center das freigegebene Postfach in das um, was es sein soll.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Fehler beim Nichtzugriff auf Sendeberechtigungen bei Verwendung eines freigegebenen Postfachs

Wenn Sie ein freigegebenes Postfach erstellt haben und dann versuchen, eine Nachricht davon zu senden, erhalten Sie möglicherweise dies:

**Diese Nachricht konnte nicht gesendet werden. Sie haben nicht die Berechtigung, die Nachricht im Namen des angegebenen Benutzers zu senden.**

Diese Meldung wird angezeigt, Microsoft 365 beim Auftreten eines Replikationslatenzproblems angezeigt wird. Sie sollte in etwa einer Stunde entfernt werden, wenn die Informationen zu Ihrem neuen freigegebenen Postfach (oder hinzugefügten Benutzer) in allen unseren Rechenzentren repliziert werden. Warten Sie eine Stunde, und versuchen Sie dann erneut, eine Nachricht zu senden.

## <a name="related-content"></a>Verwandte Inhalte

[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) (Artikel)\
[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md) (Artikel)\
[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md) (Artikel)\
[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) (Artikel)\
[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md) (Artikel)


    

