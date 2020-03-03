---
title: Informationen zu freigegebenen Postfächern
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: Freigegebene Postfächer werden verwendet, wenn mehrere Personen auf dasselbe Postfach zugreifen müssen. Erfahren Sie, was Sie wissen müssen, bevor Sie ein freigegebenes Postfach erstellen.
ms.openlocfilehash: 3bb78cc272a1920d9eab92aff50a14e345dce2e1
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362380"
---
# <a name="about-shared-mailboxes"></a>Informationen zu freigegebenen Postfächern

Freigegebene Postfächer werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen, z. B. eine E-Mail-Adresse für Unternehmensinformationen oder Support, den Empfangstresen oder andere Funktionen, die von mehreren Personen geteilt werden.

Benutzer, die über Berechtigungen für das Gruppenpostfach verfügen, können Nachrichten mit der "Senden als"- oder "Senden im Auftrag von"-Postfach-E-Mail-Adresse senden, sofern der Administrator dem jeweiligen Benutzer die entsprechende Berechtigung erteilt hat. Dies ist besonders nützlich für Hilfe-und Support Postfächer, da Benutzer e-Mails von "Contoso-Support" oder "Erstellen einer Rezeption" senden können.

Bevor Sie [ein freigegebenes Postfach erstellen](create-a-shared-mailbox.md), sollten Sie sich mit einigen Dingen vertraut machen.

- **Lizenzen:** Ihr freigegebenes Postfach kann bis zu 50 GB Daten speichern, ohne dass Sie ihm eine Lizenz zuweisen. Anschließend müssen Sie dem Postfach eine Lizenz zuweisen, um mehr Daten speichern zu können. Weitere Informationen zur Lizenzierung freigegebener Postfächer finden Sie unter [Exchange Online Limits](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits). Wenn ein freigegebenes Postfach die Speichergrenze erreicht, können Sie E-Mails noch eine Zeitlang empfangen, aber keine neuen E-Mails mehr senden. Danach wird auch der Empfang von E-Mails beendet. Absender für das Postfach erhalten einen Unzustellbarkeitsbericht.

- **Benutzerberechtigungen:** Sie müssen Benutzern Berechtigungen (Mitgliedschaft) erteilen, um das freigegebene Postfach zu verwenden. Nur Personen innerhalb Ihrer Organisation können ein freigegebenes Postfach nutzen.

- **Externe Benutzer:** Sie können nicht Personen außerhalb Ihres Unternehmens (wie Personen mit einem Gmail-Konto) Zugriff auf Ihr freigegebenes Postfach gewähren. Wenn Sie dies tun möchten, sollten Sie stattdessen eine Gruppe für Outlook erstellen. Weitere Informationen finden Sie unter [Erstellen einer Office 365 Gruppe im Admin Center](../create-groups/create-groups.md).

-  **Verwendung mit Outlook:** Zusätzlich zur Verwendung von Outlook im Internet aus Ihrem Browser für den Zugriff auf freigegebene Postfächer können Sie auch die Outlook für IOS-APP oder die Outlook für Android-App verwenden. Weitere Informationen finden Sie unter <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Hinzufügen eines freigegebenen Postfachs zu Outlook Mobile</a>. Eine weitere Möglichkeit besteht darin, eine Gruppe für Ihr freigegebenes Postfach zu erstellen. Weitere Informationen hierzu finden Sie unter [Vergleichen von Gruppen](../create-groups/compare-groups.md).  

- **Verschlüsselung:** Sie können e-Mails, die von einem freigegebenen Postfach gesendet werden, nicht verschlüsseln. Dies liegt daran, dass ein freigegebenes Postfach keinen eigenen Sicherheitskontext (Benutzername/Kennwort) aufweist, sodass ihm kein Schlüssel zugewiesen werden kann. Wenn mehr als eine Person Mitglied ist und Sie e-Mails senden/empfangen, die Sie mit ihren eigenen Schlüsseln verschlüsselt haben, können andere Mitglieder möglicherweise die e-Mails lesen, und andere möglicherweise nicht, je nachdem, mit welchem öffentlichen Schlüssel die e-Mail verschlüsselt wurde.

- **Post Fach Konvertierung:** Sie können Benutzerpostfächer in freigegebene Postfächer konvertieren. Lesen Sie dazu [Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md).

- **Administratorrollen:** Benutzer mit globalen Administrator-oder Exchange-Administratorrollen können freigegebene Postfächer erstellen.

- **Abonnementanforderungen:** Um ein freigegebenes Postfach zu erstellen, müssen Sie einen Office 365 für Unternehmen Plan abonnieren, der e-Mails (den Exchange Online Dienst) enthält. Das Office 365 Geschäfts Abonnement enthält keine e-Mails; Office 365 Business Premium.

- **Anmelden:** Ein freigegebenes Postfach ist nicht für die direkte Anmeldung durch das zugehörige Benutzerkonto vorgesehen. Sie sollten die Anmeldung für das freigegebene Postfachkonto immer blockieren und blockiert lassen.

- **Zu viele Benutzer:** Wenn zu viele designierte Benutzer gleichzeitig auf ein freigegebenes Postfach zugreifen, kann es vorkommen, dass eine Verbindung mit diesem Postfach nicht hergestellt wird. In diesem Fall können Sie die Anzahl der Benutzer verringern oder eine andere Arbeitsauslastung wie Office 365 Gruppe oder öffentlichen Ordner verwenden.

- **Löschen von Nachrichten:** Leider können Sie nicht verhindern, dass Personen Nachrichten in einem freigegebenen Postfach löschen. Die einzige Möglichkeit, dies zu verhindern, ist das Erstellen einer Office 365-Gruppe statt eines freigegebenen Postfachs. Eine Gruppe in Outlook ist wie ein freigegebenes Postfach. Einen Vergleich der beiden Informationen finden Sie unter [Compare Groups](../create-groups/compare-groups.md). Weitere Informationen zu Gruppen finden Sie unter Weitere Informationen [zu Gruppen](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)

## <a name="related-articles"></a>Verwandte Artikel

[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md)

[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md)

[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md)

[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md)

[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md)
