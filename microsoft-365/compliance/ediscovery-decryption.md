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
description: Hier erfahren Sie, wie Sie mit e-Mail-Nachrichten verbundene verschlüsselte Dokumente von Microsoft 365 eDiscovery-Tools verarbeiten
ms.openlocfilehash: 3a4a094f1da28c9a017836c099507f5af739b0b9
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951118"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Entschlüsselung in Microsoft 365 eDiscovery-Tools

Die Verschlüsselung ist ein wichtiger Bestandteil ihrer Dateischutz-und Informationsschutz Strategie. Organisationen aller Typen verwenden Verschlüsselungstechnologien, um vertrauliche Inhalte in Ihrer Organisation zu schützen und sicherzustellen, dass nur die richtigen Personen Zugriff auf diese Inhalte haben.

Um häufige eDiscovery-Aufgaben für verschlüsselte Inhalte auszuführen, mussten eDiscovery-Manager e-Mail-Nachrichteninhalte so entschlüsseln, wie Sie aus Inhalts suchen, zentralen eDiscovery-Fällen und erweiterten eDiscovery-Fällen exportiert wurden. Mit Microsoft-Verschlüsselungstechnologien verschlüsselte Inhalte standen erst nach dem Export zur Überprüfung zur Verfügung.

Um die Verwaltung verschlüsselter Inhalte im eDiscovery-Workflow zu vereinfachen, integrieren Microsoft 365 eDiscovery-Tools jetzt die Entschlüsselung von verschlüsselten Dateien, die an e-Mail-Nachrichten angefügt und in Exchange Online gesendet werden. Vor dieser neuen Funktion wurden nur die Inhalte einer durch Rechteverwaltung geschützten e-Mail-Nachricht (und keine angefügten Dateien) entschlüsselt. Wenn nun eine mit einer Microsoft-Verschlüsselungstechnologie verschlüsselte Datei an eine e-Mail-Nachricht angehängt wird, die mit den Suchkriterien übereinstimmt, wird die verschlüsselte Datei entschlüsselt, wenn die Suchergebnisse zur Überprüfung vorbereitet werden. Auf diese Weise können eDiscovery-Manager den Inhalt von verschlüsselten e-Mail-Anlagen anzeigen, wenn Sie eine Vorschau der Suchergebnisse anzeigen, und diese überprüfen, nachdem Sie zu einem Überprüfungs Satz in Advanced eDiscovery hinzugefügt wurden.

> [!NOTE]
> Starting soon Microsoft 365 eDiscovery-Tools unterstützen verschlüsselte Dokumente, die in SharePoint Online und OneDrive für Unternehmen gespeichert sind.

## <a name="supported-encryption-technologies"></a>Unterstützte Verschlüsselungstechnologien

Microsoft eDiscovery-Tools unterstützen Elemente, die mit Microsoft-Verschlüsselungstechnologien verschlüsselt sind. Zu diesen Technologien zählen Office-Nachrichtenverschlüsselung, Microsoft Information Protection (demnächst) und Azure Rights Management. Weitere Informationen zu Microsoft-Verschlüsselungstechnologien finden Sie unter [Encryption](encryption.md). Durch Verschlüsselungstechnologien von Drittanbietern verschlüsselte Inhalte werden nicht unterstützt. Dies umfasst keine Unterstützung bei der Vorschau oder beim Export von Inhalten, die mit nicht-Microsoft-Technologien verschlüsselt sind.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>eDiscovery-Aktivitäten, die verschlüsselte Elemente unterstützen

In der folgenden Tabelle sind die Aufgaben aufgeführt, die in Microsoft 365-eDiscovery-Tools ausgeführt werden und die Entschlüsselung von verschlüsselten Dateien unterstützen. Die Supportaufgaben können für eine verschlüsselte Datei ausgeführt werden, die an eine e-Mail-Nachricht angefügt ist, die den Kriterien einer Suche entspricht. Der Wert "N/A" gibt an, dass die Funktion im entsprechenden eDiscovery-Tool nicht verfügbar ist.

|eDiscovery-Aufgabe  |Inhaltssuche  |Core eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|Suchen nach Inhalten in verschlüsselten Dateien     |Ja      |Ja      |Ja      |
|Verschlüsselte Dateien in der Vorschau     |Ja      |Ja     |Ja       |
|Überprüfen von verschlüsselten Dateien in einem Überprüfungs Sätze    |Nicht zutreffend      |Nicht zutreffend        | Ja        |
|Exportieren verschlüsselter Dateien    |Ja       |Ja  |Ja    |

## <a name="requirements-for-decryption-in-ediscovery"></a>Anforderungen für die Entschlüsselung in eDiscovery

Sie müssen die RMS-Entschlüsselungs Rolle zugewiesen haben, um angefügte Dateien, die mit Microsoft-Verschlüsselungstechnologien verschlüsselt sind, anzuzeigen, zu überprüfen und zu exportieren. Sie müssen dieser Rolle auch zugewiesen sein, um verschlüsselte e-Mail-Anlagen zu überprüfen und zu Abfragen, die einem Überprüfungs Satz in Advanced eDiscovery hinzugefügt werden.

Diese Rolle wird standardmäßig der Rollengruppe eDiscovery-Manager im Office 365 Security & Compliance Center zugewiesen. Weitere Informationen zur RMS-Entschlüsselungs Rolle finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md#rms-decrypt).
