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
description: Freigegebene Postfächer werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen. Hier erfahren Sie, was Sie wissen müssen, bevor Sie ein freigegebenes Postfach erstellen.
ms.openlocfilehash: 601636f03bee93224025d286b7a74fa0f24782fb
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635534"
---
# <a name="about-shared-mailboxes"></a>Info zu freigegebenen Postfächern

Freigegebene Postfächer werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen, z. B. eine E-Mail-Adresse für Unternehmensinformationen oder Support, den Empfangstresen oder andere Funktionen, die von mehreren Personen geteilt werden.

Benutzer, die über Berechtigungen für das Gruppenpostfach verfügen, können Nachrichten mit der "Senden als"- oder "Senden im Auftrag von"-Postfach-E-Mail-Adresse senden, sofern der Administrator dem jeweiligen Benutzer die entsprechende Berechtigung erteilt hat. Dies ist besonders nützlich für Hilfe- und Support-Postfächer, da Benutzer E-Mails von "Contoso-Support" oder der "Rezeption von Gebäude A" senden können.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie [ein freigegebenes Postfach erstellen](create-a-shared-mailbox.md) müssen Sie einige Dinge wissen:

- **Lizenzen:** Ihr freigegebenes Postfach kann bis zu 50 GB Daten speichern, ohne dass Sie ihm eine Lizenz zuweisen müssen. Danach müssen Sie dem Postfach eine Lizenz zuweisen, um mehr Daten speichern zu können. Weiter Details über das Lizenzieren von freigegebenen Postfächern finden Sie unter [Exchange Online-Einschränkungen](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#StorageLimits). Wenn ein freigegebenes Postfach die Speichergrenze erreicht, können Sie E-Mails noch eine Zeitlang empfangen, aber keine neuen E-Mails mehr senden. Danach wird auch der Empfang von E-Mails beendet. Absender für das Postfach erhalten einen Unzustellbarkeitsbericht.

- **Benutzerberechtigungen:** Sie müssen den Benutzern Berechtigungen (Mitgliedschaft) für das freigegebene Postfach erteilen. Nur Personen innerhalb Ihrer Organisation können ein freigegebenes Postfach nutzen.

- **Externe Benutzer:** Sie können Personen außerhalb Ihres Unternehmens (z. B. Personen mit einem Gmail-Konto) keinen Zugriff auf Ihr freigegebenes Postfach gewähren.  Wenn Sie das tun möchten, erwägen Sie stattdessen die Erstellung einer Gruppe für Outlook.  Weitere Informationen hierzu finden Sie unter [Erstellen einer Microsoft 365-Gruppe im Admin Center](../create-groups/create-groups.md). 

- **Verwendung mit Outlook:** Neben der Verwendung von Outlook im Web über Ihren Browser für den Zugriff auf freigegebene Postfächer können Sie auch die Outlook für iOS-App oder die Outlook für Android-App verwenden. Weitere Informationen finden Sie unter [Hinzufügen eines freigegebenen Postfachs zu Outlook Mobile](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f). Eine andere Option ist die Erstellung einer Gruppe für Ihr freigegebenes Postfach. Weitere Informationen hierzu finden Sie unter [Gruppen vergleichen](../create-groups/compare-groups.md).

- **Verschlüsselung:** Sie können E-Mails, die aus einem freigegebenen Postfach gesendet werden, nicht verschlüsseln. Das liegt daran, dass ein freigegebenes Postfach keinen eigenen Sicherheitskontext (Benutzername/Kennwort) besitzt und ihm somit kein Schlüssel zugewiesen werden kann. Wenn es mehrere Mitglieder gibt und diese E-Mails senden oder empfangen, die sie mit ihren eigenen Schlüsseln verschlüsselt haben, kann es passieren, dass manche Mitglieder die E-Mail lesen können und andere wiederum nicht, je nachdem, mit welchem öffentlichen Schlüssel die E-Mail verschlüsselt wurde.

- **Postfach-Umwandlung:** Sie können Benutzerpostfächer in freigegebene Postfächer umwandeln. Weitere Informationen dazu finden Sie unter [Umwandeln eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md).

- **Administratorrollen:** Benutzer mit den Rollen „Globaler Administrator“ oder „Exchange-Administrator“ können freigegebene Postfächer erstellen.

- **Abonnement-Voraussetzungen:** Um ein freigegebenes Postfach zu erstellen, müssen Sie einen Microsoft 365 für Unternehmen-Plan abonnieren, der E-Mail einschließt (der Exchange Online-Dienst). Das Microsoft 365 Apps for Business-Abonnement schließt E-Mail nicht ein.. Microsoft 365 Business Standard schließt E-Mail nicht ein.

- **Anmelden:** Ein freigegebenes Postfach ist nicht für die direkte Anmeldung durch das zugehörige Benutzerkonto vorgesehen. Sie sollten Anmeldungen für das freigegebene Postfach-Konto immer blockieren und die Blockierung beibehalten.

- **Zu viele Benutzer:** Wenn zu viele zugewiesene Benutzer gleichzeitig auf ein freigegebenes Postfach zugreifen, können sie zeitweise keine Verbindung zu diesem Postfach herstellen. In diesem Fall können Sie die Anzahl der Benutzer reduzieren oder einen anderen Workload verwenden, z. B. eine Microsoft 365-Gruppe oder einen öffentlichen Ordner.

- **Nachrichtenlöschung:** Leider können Sie nicht verhindern, dass Personen Nachrichten in einem freigegebenen Postfach löschen. Die einzige Möglichkeit, dies zu verhindern, ist das Erstellen einer Microsoft 365-Gruppe statt eines freigegebenen Postfachs. Eine Gruppe in Outlook ist wie ein freigegebenes Postfach. Einen Vergleich dieser beiden Möglichkeiten finden Sie unter [Gruppen vergleichen](../create-groups/compare-groups.md). Weitere Informationen über Gruppen finden Sie unter [Informationen über Gruppen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).


> [!NOTE]
> Um auf ein freigegebenes Postfach zugreifen zu können, benötigt ein Benutzer eine Exchange Online-Lizenz, das freigegebene Postfach selber benötigt aber keine eigene Lizenz. Zu jedem freigegebenen Postfach gehört ein entsprechendes Benutzerkonto. Haben Sie festgestellt, dass Sie beim Erstellen des freigegebenen Postfachs nicht zur Eingabe eines Kennworts aufgefordert wurden? Das Konto verfügt über ein Kennwort, das jedoch vom System generiert wurde (unbekannt). Sie sollten nicht das Konto verwenden, um sich beim freigegebenen Postfach anzumelden. Ohne eine Lizenz sind freigegebene Postfächer auf 50 GB beschränkt. Wenn Sie die Größenbeschränkung auf 100 GB erhöhen möchten, muss dem freigegebene Postfach eine Exchange Online Plan 2-Lizenz oder eine Exchange Online Plan 1-Lizenz mit einer zusätzlichen Exchange Online-Archivierungslizenz zugewiesen werden. Auf diese Weise können Sie auch die automatische Erweiterung der Archivierung für eine unbegrenzte Menge an Archivspeicherkapazität aktivieren. Ähnlich verhält es sich, wenn Sie ein freigegebenes Postfach in die Status „Aufbewahrung für juristische Zwecke“ setzen möchten: Das freigegebene Postfach muss über eine Exchange Online Plan 2-Lizenz oder eine Exchange Online Plan 1-Lizenz mit einer zusätzlichen Exchange Online-Archivierungslizenz verfügen. Wenn Sie erweiterte Funktionen wie Microsoft Defender für Office 365, Advanced eDiscovery oder automatische Aufbewahrungsrichtlinien anwenden möchten, muss das freigegebene Postfach für diese Funktionen lizenziert sein.

## <a name="related-content"></a>Verwandte Inhalte

[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md) (Artikel)\
[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md) (Artikel)\
[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) (Artikel)\
[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md) (Artikel)\
[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md) (Artikel)