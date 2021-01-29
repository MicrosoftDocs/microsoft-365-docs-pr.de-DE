---
title: Entschlüsselung in eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Microsoft 365 eDiscovery-Tools verschlüsselte Dokumente behandeln, die an E-Mail-Nachrichten angefügt und in SharePoint Online und OneDrive for Business gespeichert sind.
ms.openlocfilehash: aeb1d927a5da24c55838fe3379451956949d8b4f
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044767"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Entschlüsselung in Microsoft 365 eDiscovery-Tools

Verschlüsselung ist ein wichtiger Bestandteil Ihrer Strategie zum Schutz von Dateien und Informationen. Organisationen aller Typen verwenden Verschlüsselungstechnologie, um vertrauliche Inhalte innerhalb ihrer Organisation zu schützen und sicherzustellen, dass nur die richtigen Personen Zugriff auf diese Inhalte haben.

Um allgemeine eDiscovery-Aufgaben für verschlüsselte Inhalte auszuführen, mussten eDiscovery-Manager E-Mail-Nachrichteninhalte entschlüsseln, während sie aus Inhaltssuchen, Core eDiscovery-Fällen und Advanced eDiscovery-Fällen exportiert wurden. Mit Microsoft Verschlüsselungstechnologien verschlüsselte Inhalte waren erst nach dem Export zur Überprüfung verfügbar.

Um die Verwaltung verschlüsselter Inhalte im eDiscovery-Workflow zu vereinfachen, umfassen die Microsoft 365 eDiscovery-Tools jetzt die Entschlüsselung verschlüsselter Dateien, die an E-Mail-Nachrichten angefügt und in Exchange Online gesendet werden. Darüber hinaus werden verschlüsselte Dokumente, die in SharePoint Online und OneDrive for Business gespeichert sind, in Advanced eDiscovery entschlüsselt. 

Vor dieser neuen Funktion wurden nur die Inhalte einer E-Mail-Nachricht entschlüsselt, die durch die Rechteverwaltung geschützt ist (und keine angefügten Dateien). Verschlüsselte Dokumente in SharePoint und OneDrive konnten während des eDiscovery-Workflows nicht entschlüsselt werden. Wenn nun eine mit einer #A0 verschlüsselte Datei an eine E-Mail-Nachricht angefügt ist oder sich in einem SharePoint- oder #A1 befindet, werden diese verschlüsselten Elemente entschlüsselt, wenn die Suchergebnisse für die Vorschau vorbereitet, einem Überprüfungssatz in Advanced eDiscovery hinzugefügt und exportiert werden. Auf diese Weise können eDiscovery-Manager den Inhalt verschlüsselter E-Mail-Anlagen und Websitedokumente anzeigen, wenn sie eine Vorschau der Suchergebnisse anzeigen, und sie überprüfen, nachdem sie einem Überprüfungssatz in Advanced eDiscovery hinzugefügt wurden.

## <a name="supported-encryption-technologies"></a>Unterstützte Verschlüsselungstechnologien

Microsoft eDiscovery-Tools unterstützen Elemente, die mit Microsoft-Verschlüsselungstechnologien verschlüsselt wurden. Zu diesen Technologien gehören office-Nachrichtenverschlüsselung, Azure Rights Management und Microsoft Information Protection (insbesondere Vertraulichkeitsbezeichnungen). Weitere Informationen zu Microsoft-Verschlüsselungstechnologien finden Sie unter ["Verschlüsselung".](encryption.md) Von Verschlüsselungstechnologien von Drittanbietern verschlüsselte Inhalte werden nicht unterstützt. Beispielsweise wird das Anzeigen oder Exportieren von Inhalten, die mit Nicht-Microsoft-Technologien verschlüsselt wurden, nicht unterstützt.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>eDiscovery-Aktivitäten, die verschlüsselte Elemente unterstützen

In der folgenden Tabelle sind die unterstützten Aufgaben aufgeführt, die in Microsoft 365 eDiscovery-Tools für verschlüsselte Dateien, die an E-Mail-Adressen und verschlüsselte Dokumente in SharePoint und OneDrive angefügt sind, ausgeführt werden können. Diese unterstützten Aufgaben können für verschlüsselte Dateien ausgeführt werden, die den Suchkriterien entsprechen. Ein Wert von gibt an, dass die Funktionalität im entsprechenden `N/A` eDiscovery-Tool nicht verfügbar ist.

|eDiscovery-Aufgabe  |Inhaltssuche  |Core eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|Suchen nach Inhalten in verschlüsselten Dateien in E-Mails und Websites     |Ja      |Ja      |Ja      |
|Vorschau verschlüsselter Dateien, die an E-Mails angefügt sind     |Ja      |Ja     |Ja       |
|Vorschau verschlüsselter Dokumente in SharePoint und OneDrive|Nein      |Nein    |Ja       |
|Überprüfen verschlüsselter Dateien in einem Überprüfungssatz    |Nicht zutreffend      |Nicht zutreffend        | Ja        |
|An E-Mails angefügte verschlüsselte Dateien exportieren    |Ja       |Ja  |Ja    |
|Exportieren verschlüsselter Dokumente in SharePoint und OneDrive    |Nein       |Nein  |Ja    |
|||||

**Hinweis:** eDiscovery unterstützt keine verschlüsselten Dateien in SharePoint und OneDrive, wenn eine Vertraulichkeitsbezeichnung, die die Verschlüsselung angewendet hat, mit einer der folgenden Einstellungen konfiguriert ist:

- Benutzer können Berechtigungen zuweisen, wenn sie die Bezeichnung manuell auf ein Dokument anwenden. Dies wird manchmal auch als *benutzerdefinierte Berechtigungen bezeichnet.*<br/>

- Der Benutzerzugriff auf das Dokument hat eine Ablaufeinstellung, die auf einen anderen Wert als **Never festgelegt ist.**

Weitere Informationen zu diesen Einstellungen finden Sie im Abschnitt "Konfigurieren von Verschlüsselungseinstellungen" in "Einschränken des Zugriffs auf Inhalte mithilfe von Vertraulichkeitsbezeichnungen zum Anwenden [der Verschlüsselung".](encryption-sensitivity-labels.md#configure-encryption-settings)

Dokumente, die mit den vorherigen Einstellungen verschlüsselt wurden, können weiterhin von einer eDiscovery-Suche zurückgegeben werden. Dies kann passieren, wenn eine Dokumenteigenschaft (z. B. Titel, Autor oder Änderungsdatum) den Suchkriterien entspricht. Obwohl diese Dokumente möglicherweise in Suchergebnissen enthalten sind, können sie nicht in der Vorschau angezeigt oder überprüft werden. Diese Dokumente bleiben auch verschlüsselt, wenn sie in Advanced eDiscovery exportiert werden.

## <a name="requirements-for-decryption-in-ediscovery"></a>Anforderungen für die Entschlüsselung in eDiscovery

Ihnen muss die Rolle "RMS-Entschlüsselung" zugewiesen sein, um Dateien in der Vorschau anzeigen, überprüfen und exportieren zu können, die mit den Verschlüsselungstechnologien von Microsoft verschlüsselt sind. Außerdem muss Ihnen diese Rolle zugewiesen werden, um verschlüsselte Dateien zu überprüfen und abfragen, die einem Überprüfungssatz in Advanced eDiscovery hinzugefügt werden.

Diese Rolle wird standardmäßig der Rollengruppe "eDiscovery-Manager" auf der Seite "Berechtigungen" im Office 365 Security & Compliance Center zugewiesen.  Weitere Informationen zur Rolle "RMS-Entschlüsselung" finden Sie unter ["Zuweisen von eDiscovery-Berechtigungen".](assign-ediscovery-permissions.md#rms-decrypt)
