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
description: Erfahren Sie, wie Microsoft 365 eDiscovery-Tools verschlüsselte Dokumente verarbeiten, die an e-Mail-Nachrichten angehängt und in SharePoint Online und OneDrive für Unternehmen gespeichert werden.
ms.openlocfilehash: df2ff218e5c62e103661889fc8c66950a4d25cab
ms.sourcegitcommit: 6759e619c45a5f8e775ad456a5dfb18c08f13f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/18/2020
ms.locfileid: "49713266"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Entschlüsselung in Microsoft 365 eDiscovery-Tools

Die Verschlüsselung ist ein wichtiger Bestandteil ihrer Dateischutz-und Informationsschutz Strategie. Organisationen aller Typen verwenden Verschlüsselungstechnologien, um vertrauliche Inhalte in Ihrer Organisation zu schützen und sicherzustellen, dass nur die richtigen Personen Zugriff auf diese Inhalte haben.

Um häufige eDiscovery-Aufgaben für verschlüsselte Inhalte auszuführen, mussten eDiscovery-Manager e-Mail-Nachrichteninhalte so entschlüsseln, wie Sie aus Inhalts suchen, zentralen eDiscovery-Fällen und erweiterten eDiscovery-Fällen exportiert wurden. Mit Microsoft-Verschlüsselungstechnologien verschlüsselte Inhalte standen erst nach dem Export zur Überprüfung zur Verfügung.

Um die Verwaltung verschlüsselter Inhalte im eDiscovery-Workflow zu vereinfachen, integrieren Microsoft 365 eDiscovery-Tools jetzt die Entschlüsselung von verschlüsselten Dateien, die an e-Mail-Nachrichten angefügt und in Exchange Online gesendet werden. Außerdem werden verschlüsselte Dokumente, die in SharePoint Online und OneDrive für Unternehmen gespeichert sind, in Advanced eDiscovery entschlüsselt. 

Vor dieser neuen Funktion wurden nur die Inhalte einer durch Rechteverwaltung geschützten e-Mail-Nachricht (und keine angefügten Dateien) entschlüsselt. Verschlüsselte Dokumente in SharePoint und OneDrive konnten während des eDiscovery-Workflows nicht entschlüsselt werden. Wenn nun eine Datei, die mit einer Microsoft-Verschlüsselungstechnologie verschlüsselt ist, an eine e-Mail-Nachricht angehängt oder in einem SharePoint-oder OneDrive-Konto gespeichert ist, werden diese verschlüsselten Elemente entschlüsselt, wenn die Suchergebnisse für die Vorschau vorbereitet, zu einer Überprüfungsgruppe in Advanced eDiscovery hinzugefügt und exportiert wurden. Auf diese Weise können eDiscovery-Manager den Inhalt von verschlüsselten e-Mail-Anlagen und Website Dokumenten anzeigen, wenn Sie eine Vorschau der Suchergebnisse anzeigen, und diese überprüfen, nachdem Sie zu einem Überprüfungs Satz in Advanced eDiscovery hinzugefügt wurden.

## <a name="supported-encryption-technologies"></a>Unterstützte Verschlüsselungstechnologien

Microsoft eDiscovery-Tools unterstützen Elemente, die mit Microsoft-Verschlüsselungstechnologien verschlüsselt sind. Zu diesen Technologien zählen Office-Nachrichtenverschlüsselung, Azure-Rechteverwaltung und Microsoft Information Protection (insbesondere Sensitivitäts Bezeichnungen). Weitere Informationen zu Microsoft-Verschlüsselungstechnologien finden Sie unter [Encryption](encryption.md). Durch Verschlüsselungstechnologien von Drittanbietern verschlüsselte Inhalte werden nicht unterstützt. Beispielsweise wird die Vorschau oder das Exportieren von Inhalten, die mit nicht-Microsoft-Technologien verschlüsselt sind, nicht unterstützt.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>eDiscovery-Aktivitäten, die verschlüsselte Elemente unterstützen

In der folgenden Tabelle sind die unterstützten Aufgaben aufgeführt, die in Microsoft 365-eDiscovery-Tools für verschlüsselte Dateien an e-Mail-Massagen und verschlüsselte Dokumente in SharePoint und OneDrive ausgeführt werden können. Diese unterstützten Aufgaben können für eine verschlüsselte Datei ausgeführt werden, die den Kriterien einer Suche entsprechen. Der Wert "N/A" gibt an, dass die Funktionalität im entsprechenden eDiscovery-Tool nicht verfügbar ist.

|eDiscovery-Aufgabe  |Inhaltssuche  |Core eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|Suchen nach Inhalten in verschlüsselten Dateien in e-Mails und Websites     |Ja      |Ja      |Ja      |
|Vorschau der an e-Mail angefügten verschlüsselten Dateien     |Ja      |Ja     |Ja       |
|Anzeigen von verschlüsselten Dokumenten in SharePoint und OneDrive|Nein      |Nein    |Ja       |
|Überprüfen von verschlüsselten Dateien in einem Überprüfungs Sätze    |Nicht zutreffend      |Nicht zutreffend        | Ja        |
|Exportieren verschlüsselter Dateien, die an e-Mail angefügt sind    |Ja       |Ja  |Ja    |
|Exportieren von verschlüsselten Dokumenten in SharePoint und OneDrive    |Nein       |Nein  |Ja    |
|||||

## <a name="requirements-for-decryption-in-ediscovery"></a>Anforderungen für die Entschlüsselung in eDiscovery

Sie müssen die RMS-Entschlüsselungs Rolle zugewiesen haben, um Dateien, die mit Microsoft-Verschlüsselungstechnologien verschlüsselt sind, anzuzeigen, zu überprüfen und zu exportieren. Sie müssen dieser Rolle auch zugewiesen sein, um verschlüsselte Dateien zu überprüfen und zu Abfragen, die einem Überprüfungs Satzes in Advanced eDiscovery hinzugefügt werden.

Diese Rolle wird standardmäßig der Rollengruppe eDiscovery-Manager auf der Seite **Berechtigungen** im Office 365 Security & Compliance Center zugewiesen. Weitere Informationen zur RMS-Entschlüsselungs Rolle finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md#rms-decrypt).
