---
title: Info zu freigegebenen Postfächern
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
description: Freigegebene Postfächer werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen. Erfahren Sie, was Sie wissen müssen, bevor Sie ein freigegebenes Postfach erstellen.
ms.openlocfilehash: c8d29ac2dfe8670181064e61a7fba145ae00fed1
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058447"
---
# <a name="about-shared-mailboxes"></a>Info zu freigegebenen Postfächern

Freigegebene Postfächer werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen, z. B. eine E-Mail-Adresse für Unternehmensinformationen oder Support, den Empfangstresen oder andere Funktionen, die von mehreren Personen geteilt werden.

Benutzer, die über Berechtigungen für das Gruppenpostfach verfügen, können Nachrichten mit der "Senden als"- oder "Senden im Auftrag von"-Postfach-E-Mail-Adresse senden, sofern der Administrator dem jeweiligen Benutzer die entsprechende Berechtigung erteilt hat. Dies ist besonders nützlich für Hilfe- und Support-Postfächer, da Benutzer E-Mails von "Contoso-Support" oder der "Rezeption von Gebäude A" senden können.

Bevor Sie [ein freigegebenes Postfach erstellen,](create-a-shared-mailbox.md)sollten Sie dies wissen:

- **Lizenzen:** Ihr freigegebenes Postfach kann bis zu 50 GB Daten speichern, ohne dass Sie ihm eine Lizenz zuweisen. Anschließend müssen Sie dem Postfach eine Lizenz zuweisen, um mehr Daten speichern zu können. Weitere Informationen zur Lizenzierung freigegebener Postfächer finden Sie unter [Exchange Online-Beschränkungen.](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits) Wenn ein freigegebenes Postfach die Speichergrenze erreicht, können Sie E-Mails noch eine Zeitlang empfangen, aber keine neuen E-Mails mehr senden. Danach wird auch der Empfang von E-Mails beendet. Absender für das Postfach erhalten einen Unzustellbarkeitsbericht.

- **Benutzerberechtigungen:** Sie müssen Benutzern Berechtigungen (Mitgliedschaft) für die Verwendung des freigegebenen Postfachs erteilen. Nur Personen innerhalb Ihrer Organisation können ein freigegebenes Postfach nutzen.

- **Externe Benutzer:** Sie können Personen außerhalb Ihres Unternehmens (z. B. Personen mit einem Gmail-Konto) keinen Zugriff auf Ihr freigegebenes Postfach geben. Wenn Sie dies tun möchten, sollten Sie stattdessen eine Gruppe für Outlook erstellen. Weitere Informationen finden Sie unter [Erstellen einer Microsoft 365-Gruppe im Admin Center.](../create-groups/create-groups.md)

- **Verwenden mit Outlook:** Zusätzlich zur Verwendung von Outlook im Web über Ihren Browser für den Zugriff auf freigegebene Postfächer können Sie auch die Outlook für iOS-App oder die Outlook für Android-App verwenden. Weitere Informationen finden Sie unter [Hinzufügen eines freigegebenen Postfachs zu Outlook Mobile](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f). Eine weitere Möglichkeit besteht in der Erstellung einer Gruppe für Ihr freigegebenes Postfach. Weitere Informationen hierzu finden Sie unter [Vergleichen von Gruppen](../create-groups/compare-groups.md).

- **Verschlüsselung:** Von einem freigegebenen Postfach gesendete E-Mails können nicht verschlüsselt werden. Dies liegt daran, dass ein freigegebenes Postfach nicht über einen eigenen Sicherheitskontext (Benutzername/Kennwort) verfügt, sodass ihm kein Schlüssel zugewiesen werden kann. Wenn mehrere Personen Mitglied sind und sie E-Mails senden/empfangen, die sie mit ihren eigenen Schlüsseln verschlüsselt haben, können andere Mitglieder die E-Mail möglicherweise lesen, andere möglicherweise nicht, je nachdem, mit welchem öffentlichen Schlüssel die E-Mail verschlüsselt wurde.

- **Postfachkonvertierung:** Sie können Benutzerpostfächer in freigegebene Postfächer konvertieren. Lesen Sie dazu [Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md).

- **Administratorrollen:** Benutzer mit globalen Administrator- oder Exchange-Administratorrollen können freigegebene Postfächer erstellen.

- **Abonnementanforderungen:** Zum Erstellen eines freigegebenen Postfachs müssen Sie einen Microsoft 365 Business-Plan abonnieren, der E-Mails (den Exchange Online-Dienst) enthält. Das Microsoft 365 Apps for Business-Abonnement enthält keine E-Mails. Microsoft 365 Business Standard enthält E-Mails.

- **Anmelden:** Ein freigegebenes Postfach ist nicht für die direkte Anmeldung über das zugeordnete Benutzerkonto vorgesehen. Sie sollten die Anmeldung für das freigegebene Postfachkonto immer blockieren und blockieren.

- **Zu viele Benutzer:** Wenn zu viele festgelegte Benutzer gleichzeitig auf ein freigegebenes Postfach zugreifen, können sie möglicherweise zeitweise keine Verbindung mit diesem Postfach herstellen. In diesem Fall können Sie die Anzahl der Benutzer reduzieren oder eine andere Arbeitsauslastung verwenden, z. B. eine Microsoft 365-Gruppe oder einen öffentlichen Ordner.

- **Nachrichtenlöschung:** Leider können Sie nicht verhindern, dass Personen Nachrichten in einem freigegebenen Postfach löschen. Die einzige Möglichkeit besteht in der Erstellung einer Microsoft 365-Gruppe anstelle eines freigegebenen Postfachs. Eine Gruppe in Outlook ist wie ein freigegebenes Postfach. Einen Vergleich der beiden Finden Sie unter Vergleichen [von Gruppen.](../create-groups/compare-groups.md) Weitere Informationen zu Gruppen finden Sie [unter Weitere Informationen zu Gruppen.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)


> [!NOTE]
> Für den Zugriff auf ein freigegebenes Postfach muss ein Benutzer über eine Exchange Online-Lizenz verfügen, für das freigegebene Postfach ist jedoch keine separate Lizenz erforderlich. Ohne Lizenz sind freigegebene Postfächer auf 50 GB beschränkt. Um die Größenbeschränkung auf 100 GB zu erhöhen, muss dem freigegebenen Postfach eine Exchange Online Plan 2-Lizenz oder eine Exchange Online Plan 1-Lizenz mit einer Exchange Online-Archivierung-Add-On-Lizenz zugewiesen werden. Dadurch können Sie auch die Archivierung mit automatischer Erweiterung für eine unbegrenzte Menge an Archivspeicherkapazität aktivieren. Ebenso muss das freigegebene Postfach über eine Exchange Online Plan 2-Lizenz oder eine Exchange Online Plan 1-Lizenz mit einer Exchange Online-Archivierung-Add-On-Lizenz verfügen, wenn Sie für ein freigegebenes Postfach das Rechtsstreitigkeiten aktivieren möchten. Wenn Sie erweiterte Features wie Microsoft Defender für Office 365, Advanced eDiscovery oder automatische Aufbewahrungsrichtlinien anwenden möchten, muss das freigegebene Postfach für diese Features lizenziert werden.

## <a name="related-articles"></a>Verwandte Artikel

[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md)

[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md)

[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md)

[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md)

[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md)
