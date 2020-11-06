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
ROBOTS: NOINDEX, NOFOLLOW
description: Hier erfahren Sie, wie Sie mit e-Mail-Nachrichten verbundene verschlüsselte Dokumente von Microsoft 365 eDiscovery-Tools verarbeiten
ms.openlocfilehash: b7c1dc20b8e400b9880cc00a88a2d23a4b6d1979
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925584"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Entschlüsselung in Microsoft 365 eDiscovery-Tools

Organisationen verwenden Verschlüsselungstechnologien, um vertrauliche Inhalte in Ihrer Organisation zu schützen und sicherzustellen, dass nur die richtigen Personen Zugriff auf diese Inhalte haben. Unternehmen verwenden verschiedene Verschlüsselungstypen, sowohl Microsoft-Verschlüsselungstechnologien als auch drittanbietertechnologien, um Ihre Sicherheitsanforderungen zu erfüllen und Ihre vertraulichen Informationen zu schützen.

Für die Verwaltung von verschlüsselten Inhalten im eDiscovery-Workflow in Microsoft 365 ist bislang eine spezielle Behandlung von verschlüsselten Elementen in Abhängigkeit von der Art der verwendeten Verschlüsselung und der spezifischen Phase im Workflow erforderlich. Dies wurde in erster Linie durch Entschlüsseln von e-Mail-Nachrichteninhalten beim Exportieren aus Inhalts suchen, zentralen eDiscovery-Fällen und erweiterten eDiscovery-Fällen erreicht. Mit Microsoft-Verschlüsselungstechnologien verschlüsselte Inhalte konnten erst in der Vorschau angezeigt werden, wenn Sie exportiert wurden. In Advanced eDiscovery wurde der verschlüsselte Inhalt mit einem Verarbeitungsfehler gekennzeichnet, der erforderte, dass Sie das verschlüsselte Element herunterladen, es entschlüsseln und dann die entschlüsselte Datei in einen Überprüfungs-Datensatz hochladen.

Um die Verwaltung verschlüsselter Inhalte im eDiscovery-Workflow zu vereinfachen, können Microsoft 365 eDiscovery-Tools verschlüsselte Dateien entschlüsseln, die an e-Mail-Nachrichten angehängt und in Exchange Online gesendet werden. Vor dieser neuen Funktion wurde nur der Inhalt einer durch Rechteverwaltung geschützten e-Mail-Nachricht (und keine angefügten Dateien) entschlüsselt. Wenn nun eine mit einer Microsoft-Verschlüsselungstechnologie verschlüsselte Datei an eine e-Mail-Nachricht angehängt wird, die mit den Suchkriterien übereinstimmt, wird die verschlüsselte Datei entschlüsselt, wenn die Suchergebnisse für die Vorschau vorbereitet werden. Auf diese Weise können eDiscovery-Manager den Inhalt von verschlüsselten e-Mail-Anlagen bei der Vorschau der Suchergebnisse anzeigen.

## <a name="supported-encryption-technologies"></a>Unterstützte Verschlüsselungstechnologien

Microsoft eDiscovery-Tools unterstützen Elemente, die mit Microsoft-Verschlüsselungstechnologien verschlüsselt sind. Zu diesen Technologien zählen Office-Nachrichtenverschlüsselung, Microsoft Information Protection (Sensitivitäts Bezeichnungen) und Azure Rights Management. Weitere Informationen zu Microsoft-Verschlüsselungstechnologien finden Sie unter [Encryption](encryption.md). Durch Verschlüsselungstechnologien von Drittanbietern verschlüsselte Inhalte werden nicht unterstützt. Dies umfasst keine Unterstützung bei der Vorschau oder beim Export von Inhalten, die mit nicht-Microsoft-Technologien verschlüsselt sind.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>eDiscovery-Aktivitäten, die verschlüsselte Elemente unterstützen

In der folgenden Tabelle sind die Aufgaben aufgeführt, die in Microsoft 365-eDiscovery-Tools ausgeführt werden und die Entschlüsselung von verschlüsselten Dateien unterstützen. Die Supportaufgaben können für eine verschlüsselte Datei ausgeführt werden, die an eine e-Mail-Nachricht angefügt ist, die den Kriterien einer Suche entspricht. Der Wert "N/A" gibt an, dass die Funktion im entsprechenden eDiscovery-Tool nicht verfügbar ist.

|eDiscovery-Aufgabe  |Inhaltssuche  |Core eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|Suchen nach Inhalten in verschlüsselten Dateien     |Nein      |Nein      |Nein      |
|Verschlüsselte Dateien in der Vorschau     |Ja      |Ja     |Ja       |
|Überprüfen von verschlüsselten Dateien in einem Überprüfungs Sätze    |Nicht zutreffend      |Nicht zutreffend        | Ja        |
|Exportieren verschlüsselter Dateien    |Ja       |Ja  |Ja    |

## <a name="requirements-for-decryption-in-ediscovery"></a>Anforderungen für die Entschlüsselung in eDiscovery

Sie müssen die RMS-Entschlüsselungs Rolle zugewiesen haben, um angefügte Dateien, die mit Microsoft-Verschlüsselungstechnologien verschlüsselt sind, anzuzeigen, zu überprüfen und zu exportieren. Sie müssen dieser Rolle auch zugewiesen sein, um verschlüsselte e-Mail-Anlagen zu überprüfen und zu Abfragen, die einem Überprüfungs Satz in Advanced eDiscovery hinzugefügt werden.

Diese Rolle wird standardmäßig der Rollengruppe eDiscovery-Manager im Office 365 Security & Compliance Center zugewiesen. Weitere Informationen zur RMS-Entschlüsselungs Rolle finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md#rms-decrypt).
