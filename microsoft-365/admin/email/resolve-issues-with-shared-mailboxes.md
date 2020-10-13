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
search.appverid:
- BCS160
- MET150
- MOE150
description: Versuchen Sie diese Lösungen, wenn Probleme mit freigegebenen Postfächern auftreten.
ms.openlocfilehash: c889d3aa2fab8c2dce4cc2a8a00ef49a905363a1
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445507"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Beheben von Problemen mit freigegebenen Postfächern

Wenn beim Erstellen oder Verwenden eines freigegebenen Postfachs Fehlermeldungen angezeigt werden, versuchen Sie es mit den folgenden Lösungsmöglichkeiten. 

## <a name="error-when-creating-shared-mailboxes"></a>Fehler beim Erstellen freigegebener Postfächer
<a name="bkmk_Fix"> </a>

Wenn die Fehlermeldung angezeigt wird, **wird die Proxyadresse "SMTP: <freigegebener Postfachname \> " bereits von den Proxyadressen oder legacyExchangeDN von " \<name> " verwendet. Wählen Sie eine andere Proxyadresse aus**, d. h., Sie versuchen, dem freigegebenen Postfach einen bereits verwendeten Namen zu geben. Beispiel: Sie möchten freigegebenen Postfächern die Namen "info@domaene1" und "info@domaene2" geben. Sie können auf zwei Arten vorgehen:

  - Verwenden Sie Windows PowerShell. In diesem Blogbeitrag finden Sie Anweisungen: [Erstellen freigegebener Postfächer mit gleichem Alias in verschiedenen Domänen](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Nennen Sie das zweite freigegebene Postfach etwas anderes als den Anfang, um den Fehler zu umgehen. Benennen Sie dann im Admin Center das freigegebene Postfach So um, wie es sein soll.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Fehler beim Senden von Berechtigungen bei Verwendung eines freigegebenen Postfachs

Wenn Sie ein freigegebenes Postfach erstellt und anschließend versuchen, eine Nachricht daraus zu senden, erhalten Sie möglicherweise Folgendes:

**Diese Nachricht konnte nicht gesendet werden. Sie verfügen nicht über die Berechtigung, die Nachricht im Namen des angegebenen Benutzers zu senden.**

Diese Meldung wird angezeigt, wenn bei Microsoft 365 ein Problem mit der Replikationswartezeit auftritt. Es sollte in einer Stunde oder so verschwinden, wenn die Informationen zu Ihrem neuen freigegebenen Postfach (oder hinzugefügter Benutzer) in allen unseren Rechenzentren repliziert werden. Warten Sie eine Stunde, und versuchen Sie dann erneut, eine Nachricht zu senden.

## <a name="related-articles"></a>Verwandte Artikel

[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md)

[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md)

[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md)

[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md)

[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md)


    

