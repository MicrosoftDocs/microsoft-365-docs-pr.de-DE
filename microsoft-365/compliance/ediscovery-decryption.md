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
description: Erfahren Sie, wie Microsoft 365 eDiscovery-Tools verschlüsselte Dokumente verarbeiten, die an E-Mail-Nachrichten angefügt und in SharePoint Online und OneDrive for Business gespeichert sind.
ms.openlocfilehash: ad7ee9816e83caa49e437e1723655162a44c93fa
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034068"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Entschlüsselung in Microsoft 365 eDiscovery-Tools

Verschlüsselung ist ein wichtiger Bestandteil Ihrer Strategie zum Schutz von Dateien und Informationen. Organisationen aller Arten verwenden Verschlüsselungstechnologie, um vertrauliche Inhalte innerhalb ihrer Organisation zu schützen und sicherzustellen, dass nur die richtigen Personen Zugriff auf diese Inhalte haben.

Um allgemeine eDiscovery-Aufgaben für verschlüsselten Inhalt auszuführen, mussten eDiscovery-Manager E-Mail-Nachrichteninhalte beim Exportieren aus Inhaltssuchen, Core eDiscovery-Fällen und Advanced eDiscovery-Fällen entschlüsseln. Mit Microsoft-Verschlüsselungstechnologien verschlüsselte Inhalte waren erst nach dem Export zur Überprüfung verfügbar.

Um die Verwaltung verschlüsselter Inhalte im eDiscovery-Workflow zu vereinfachen, umfassen Microsoft 365 eDiscovery-Tools jetzt die Entschlüsselung verschlüsselter Dateien, die an E-Mail-Nachrichten angefügt und in Exchange Online gesendet werden. Darüber hinaus werden verschlüsselte Dokumente, die in SharePoint Online und OneDrive for Business gespeichert sind, in Advanced eDiscovery entschlüsselt.

Vor dieser neuen Funktion wurden nur der Inhalt einer durch die Rechteverwaltung geschützten E-Mail-Nachricht (und nicht angefügte Dateien) entschlüsselt. Verschlüsselte Dokumente in SharePoint und OneDrive konnten während des eDiscovery-Workflows nicht entschlüsselt werden. Wenn nun eine Datei, die mit einer #A0 verschlüsselt ist, an eine E-Mail-Nachricht angefügt ist oder sich in einem SharePoint- oder OneDrive-Konto befindet, werden diese verschlüsselten Elemente entschlüsselt, wenn die Suchergebnisse für die Vorschau vorbereitet, einem Überprüfungssatz in Advanced eDiscovery hinzugefügt und exportiert werden. Auf diese Weise können eDiscovery-Manager den Inhalt von verschlüsselten E-Mail-Anlagen und Websitedokumenten anzeigen, wenn sie eine Vorschau der Suchergebnisse anzeigen und diese überprüfen, nachdem sie einem Überprüfungssatz in Advanced eDiscovery hinzugefügt wurden.

## <a name="supported-encryption-technologies"></a>Unterstützte Verschlüsselungstechnologien

Microsoft eDiscovery-Tools unterstützen Elemente, die mit Microsoft-Verschlüsselungstechnologien verschlüsselt sind. Diese Technologien sind Azure Rights Management und Microsoft Information Protection (insbesondere Vertraulichkeitsbezeichnungen). Weitere Informationen zu Microsoft-Verschlüsselungstechnologien finden Sie unter [Encryption](encryption.md). Von Verschlüsselungstechnologien von Drittanbietern verschlüsselte Inhalte werden nicht unterstützt. Beispielsweise wird das Anzeigen oder Exportieren von Inhalten, die mit Nicht-Microsoft-Technologien verschlüsselt sind, nicht unterstützt.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>eDiscovery-Aktivitäten, die verschlüsselte Elemente unterstützen

In der folgenden Tabelle sind die unterstützten Aufgaben aufgeführt, die in Microsoft 365 eDiscovery-Tools für verschlüsselte Dateien ausgeführt werden können, die an E-Mail-Nachrichten und verschlüsselte Dokumente in SharePoint und OneDrive angefügt sind. Diese unterstützten Aufgaben können für verschlüsselte Dateien ausgeführt werden, die den Kriterien einer Suche entsprechen. Ein Wert von gibt an, dass die Funktionalität im entsprechenden `N/A` eDiscovery-Tool nicht verfügbar ist.

|eDiscovery-Aufgabe  |Inhaltssuche  |Core eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|Suchen nach Inhalten in verschlüsselten Dateien in E-Mails und Websites     |Ja      |Ja      |Ja      |
|Vorschau verschlüsselter Dateien, die an E-Mails angefügt sind     |Ja      |Ja     |Ja       |
|Vorschau verschlüsselter Dokumente in SharePoint und OneDrive|Nein      |Nein    |Ja       |
|Überprüfen verschlüsselter Dateien in einem Überprüfungssatz    |Nicht zutreffend      |Nicht zutreffend        | Ja        |
|Exportieren verschlüsselter Dateien, die an E-Mails angefügt sind    |Ja       |Ja  |Ja    |
|Exportieren verschlüsselter Dokumente in SharePoint und OneDrive    |Nein       |Nein  |Ja    |
|||||

**Hinweis:** eDiscovery unterstützt keine verschlüsselten Dateien in SharePoint und OneDrive, wenn eine Vertraulichkeitsbezeichnung, die die Verschlüsselung angewendet hat, mit einer der folgenden Einstellungen konfiguriert ist:

- Benutzer können Berechtigungen zuweisen, wenn sie die Bezeichnung manuell auf ein Dokument anwenden. Dies wird manchmal als benutzerdefinierte *Berechtigungen bezeichnet.*<br/>

- Der Benutzerzugriff auf das Dokument verfügt über eine Ablaufeinstellung, die auf einen anderen Wert als **Never festgelegt ist.**

Weitere Informationen zu diesen Einstellungen finden Sie im Abschnitt "Konfigurieren von Verschlüsselungseinstellungen" unter Einschränken des Zugriffs auf Inhalte mithilfe von Vertraulichkeitsbezeichnungen zum Anwenden [der Verschlüsselung.](encryption-sensitivity-labels.md#configure-encryption-settings)

Dokumente, die mit den vorherigen Einstellungen verschlüsselt wurden, können weiterhin von einer eDiscovery-Suche zurückgegeben werden. Dies kann vorkommen, wenn eine Dokumenteigenschaft (z. B. Titel, Autor oder Änderungsdatum) den Suchkriterien entspricht. Obwohl diese Dokumente möglicherweise in Suchergebnissen enthalten sind, können sie nicht in der Vorschau angezeigt oder überprüft werden. Diese Dokumente bleiben auch verschlüsselt, wenn sie in Advanced eDiscovery exportiert werden.

## <a name="requirements-for-decryption-in-ediscovery"></a>Anforderungen für die Entschlüsselung in eDiscovery

Ihnen muss die Rolle RMS Decrypt zugewiesen werden, um dateien, die mit Microsoft-Verschlüsselungstechnologien verschlüsselt sind, anzuzeigen, zu überprüfen und zu exportieren. Außerdem muss Ihnen diese Rolle zugewiesen werden, um verschlüsselte Dateien zu überprüfen und zu abfragen, die einem Überprüfungssatz in Advanced eDiscovery hinzugefügt wurden.

Diese Rolle wird standardmäßig der Rollengruppe eDiscovery  Manager auf der Seite Berechtigungen im Office 365 Security & Compliance Center zugewiesen. Weitere Informationen zur Rolle "RMS Decrypt" finden Sie unter [Assign eDiscovery permissions](assign-ediscovery-permissions.md#rms-decrypt).
