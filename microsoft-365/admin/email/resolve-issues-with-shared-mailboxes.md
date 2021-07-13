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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: Beim Einrichten freigegebener Postfächer können Fehler auftreten. Probieren Sie diese Lösungen aus, wenn Probleme mit freigegebenen Postfächern auftreten.
ms.openlocfilehash: ae76bc1cb97c44087be57adc7791ea8814b94b40
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393943"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Beheben von Problemen mit freigegebenen Postfächern

Wenn beim Erstellen oder Verwenden eines freigegebenen Postfachs Fehlermeldungen angezeigt werden, probieren Sie diese möglichen Lösungen aus. 

## <a name="error-when-creating-shared-mailboxes"></a>Fehler beim Erstellen freigegebener Postfächer
<a name="bkmk_Fix"> </a>

Wenn die Fehlermeldung angezeigt **wird, wird die Proxyadresse "smtp:<freigegebener Postfachname" \> bereits von den Proxyadressen oder LegacyExchangeDN von " \<name> verwendet. Wählen Sie eine andere Proxyadresse** aus. Dies bedeutet, dass Sie versuchen, dem freigegebenen Postfach einen Namen zu geben, der bereits verwendet wird. Beispiel: Sie möchten freigegebenen Postfächern die Namen "info@domaene1" und "info@domaene2" geben. Sie können auf zwei Arten vorgehen:

  - Verwenden Sie Windows PowerShell. Anweisungen finden Sie in diesem Blogbeitrag: [Erstellen freigegebener Postfächer mit demselben Alias in verschiedenen Domänen](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Benennen Sie das zweite freigegebene Postfach anders als zu Beginn, um den Fehler zu umgehen. Benennen Sie dann im Admin Center das freigegebene Postfach in das gewünschte Postfach um.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Fehler beim Nichtbeachten von Sendeberechtigungen bei Verwendung eines freigegebenen Postfachs

Wenn Sie ein freigegebenes Postfach erstellt und dann versuchen, eine Nachricht daraus zu senden, erhalten Sie möglicherweise Folgendes:

**Diese Nachricht konnte nicht gesendet werden. Sie verfügen nicht über die Berechtigung, die Nachricht im Auftrag des angegebenen Benutzers zu senden.**

Diese Meldung wird angezeigt, wenn bei Microsoft 365 ein Replikationslatenzproblem auftritt. Sie sollte in etwa einer Stunde entfernt sein, wenn die Informationen zu Ihrem neuen freigegebenen Postfach (oder dem hinzugefügten Benutzer) in allen unseren Rechenzentren repliziert werden. Warten Sie eine Stunde, und versuchen Sie es dann erneut, um eine Nachricht zu senden.

## <a name="related-content"></a>Verwandte Inhalte

[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) (Artikel)\
[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md) (Artikel)\
[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md) (Artikel)\
[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) (Artikel)\
[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md) (Artikel)


    

