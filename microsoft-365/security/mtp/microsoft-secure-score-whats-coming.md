---
title: Was kommt in Microsoft Secure Score vor?
description: Beschreibt Microsoft Secure Score im Microsoft 365 Security Center, wie Details berechnet werden und welche Sicherheitsadministratoren erwarten können.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, sicheres Ergebnis, Sicherheitscenter, Verbesserungs Aktionen
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4d445d4c917a46b12592308f599570725ace8e9d
ms.sourcegitcommit: 6c7f6ef98c321c80a9254c10bbbb917895b5c156
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "42322564"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Was kommt in Microsoft Secure Score vor?

Um Microsoft Secure Score zu einem besseren Vertreter ihrer Sicherheitsposition zu machen und die Benutzerfreundlichkeit zu verbessern, werden wir in naher Zukunft einige Änderungen vornehmen. Ihre Punktzahl und die maximal mögliche Punktzahl ändern sich. Dies impliziert jedoch keine Änderung ihrer Sicherheitsposition.

Informationen zu den neuesten Änderungen finden Sie unter [What es New in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)

## <a name="march-2nd-2020"></a>2. März 2020

### <a name="removing-improvement-actions-from-intune"></a>Entfernen von Verbesserungs Aktionen aus InTune

Nach einer Auswertung der von InTune bereitgestellten Microsoft Secure Score Improvement-Aktionen wurde entschieden, dass Sie keine nützliche Darstellung der Sicherheitslage von Geräten in Organisationen darstellen. Anstatt sich auf Richtlinien zu konzentrieren, arbeiten wir daran, Sicherheitskontrollen einzuführen, die den Konfigurationsstatus der Geräte direkt bewerten.

Die folgenden InTune-Verbesserungs Aktionen werden entfernt:

- Aktivieren der Verwaltung von mobilen Geräten in Microsoft InTune
- Erstellen einer Microsoft InTune-Konformitätsrichtlinie für Android
- Erstellen einer Microsoft InTune-Konformitätsrichtlinie für Android for Work
- Erstellen einer Microsoft InTune-App-Schutzrichtlinie für Android
- Erstellen einer Microsoft InTune-App-Schutzrichtlinie für IOS
- Geräte markieren, für die keine Microsoft InTune-Konformitätsrichtlinie als nicht kompatibel zugewiesen ist
- Erstellen einer Microsoft InTune-Konformitätsrichtlinie für IOS
- Erstellen einer Microsoft InTune-Konformitätsrichtlinie für macOS
- Erstellen einer Microsoft InTune-Konformitätsrichtlinie für Windows
- Erstellen eines Microsoft InTune-Konfigurationsprofils für Android
- Erstellen eines Microsoft InTune-Konfigurationsprofils für Android for Work
- Erstellen eines Microsoft InTune-Konfigurationsprofils für macOS
- Erstellen eines Microsoft InTune-Konfigurationsprofils für IOS
- Erstellen eines Microsoft InTune-Konfigurationsprofils für Windows
- Aktivieren der verbesserten Jailbreak-Erkennung in Microsoft InTune
- Erfordern, dass alle Geräte gepatcht werden, Virenschutz und Firewalls aktiviert sind
- Aktivieren der Integration von Windows Defender ATP in Microsoft InTune
- Erstellen einer Microsoft InTune-Windows-Informationsschutz Richtlinie
- Erfordern von erweiterten Sicherheitskonfigurationen für alle Geräte
- Bericht überprüfen blockierter Geräte wöchentlich

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>Entfernen von Verbesserungs Aktionen, die die Erwartungen für eine zuverlässige Messung nicht erfüllen 

Um sicherzustellen, dass die Microsoft Secure Score sinnvoll ist und dass jede Verbesserungs Aktion messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungs Aktionen.

- Aktivieren der Aufzeichnung von Überwachungsdaten
- Ermitteln riskanter und nicht kompatibler Shadow-IT-Anwendungen
- Überprüfen von Berechtigungen & blockieren riskanter OAuth-Anwendungen, die mit Ihrer Umgebung verbunden sind
- Einrichten der Versionsverwaltung in SharePoint Online-Dokumentbibliotheken

### <a name="mfa-improvement-action-updates"></a>Aktualisierung der MFA-Verbesserungs Aktionen

Um den Anforderungen an Unternehmen Rechnung zu tragen, beim Anwenden von Richtlinien, die mit Ihrem Unternehmen zusammenarbeiten, die höchste Sicherheit zu gewährleisten, entfernt Microsoft Secure Score drei Verbesserungs Aktionen, die sich auf die mehrstufige Authentifizierung konzentrieren, und fügt zwei hinzu.

Die drei, die entfernt werden:

- Registrieren aller Benutzer für mehrstufige Authentifizierung
- MFA für alle Benutzer erforderlich
- MFA für Azure AD privilegierten Rollen erforderlich

Neue Verbesserungs Aktionen hinzugefügt:

- Sicherstellen, dass alle Benutzer mehrstufige Authentifizierung für sicheren Zugriff ausführen können
- MFA für Administratorrollen erforderlich

 Für diese neuen Verbesserungs Aktionen müssen Sie die Benutzer oder Administratoren für die mehrstufige Authentifizierung (MFA) in Ihrem Verzeichnis registrieren und die richtigen Richtlinien festlegen, die Ihren organisatorischen Anforderungen entsprechen. Das Hauptziel besteht in der Flexibilität bei gleichzeitiger Sicherstellung, dass alle Benutzer und Administratoren sich mit mehreren Faktoren oder mit risikobasierten Identitäts Überprüfungs Ansagen authentifizieren können. Dies kann die Form haben, dass mehrere Richtlinien mit bereichsbezogenen Entscheidungen angewendet werden oder Sicherheitsstandards (am 16. März) festgelegt werden, mit denen Microsoft entscheiden kann, wann die Benutzer für MFA herausgefordert werden sollen.

### <a name="removing-review-improvement-actions"></a>Entfernen von Verbesserungs Aktionen für "überprüfen"

Eines der Prinzipien von Secure Score ist, dass die Bewertung standardisiert und leicht zu beziehen ist. Durch Verbesserungs Aktionen, die nicht messbar oder handlungsbereit sind, wurde eine Verwechslung verursacht. Ein sicheres Ergebnis von Microsoft ist nur dann sinnvoll, wenn jede Empfehlung einen klaren Effekt auf die Bewertung haben kann. Überarbeitungs Verbesserungs Aktionen werden nicht auf den gleichen Standard wie andere Verbesserungs Aktionen gemessen.  

Aus diesen Gründen werden alle Verbesserungs Aktionen, die eine Überarbeitungs Kadenz erforderten, vorübergehend entfernt. Ihrerseits ist keine Aktion erforderlich.

## <a name="march-16th-2020"></a>16. März 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Entfernen von Verbesserungs Aktionen, die nicht den Erwartungen für eine zuverlässige Messung entsprechen oder keine sinnvolle Darstellung der Sicherheitsposition bieten

Um sicherzustellen, dass die Microsoft Secure Score sinnvoll ist und dass jede Verbesserungs Aktion messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungs Aktionen.

- Speichern von Benutzerdokumenten in OneDrive für Unternehmen
- Einrichten Office 365 Richtlinien für ATP-sichere Anlagen
- Einrichten Office 365 sicherer Links zum Überprüfen von URLs
- Post Fach Delegierung nicht zulassen
- Zulassen von anonymen Gast Freigabelinks für Websites und Dokumente
- Aktivieren der Cloud-App-Sicherheitskonsole

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Unterstützen von Sicherheitsstandards für Azure AD Verbesserungs Aktionen

Microsoft Secure Score wird Update Verbesserungs Aktionen zur Unterstützung von [Sicherheitsstandards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), die es einfacher machen, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.

Dies wirkt sich auf die folgenden Verbesserungs Aktionen aus:

- Sicherstellen, dass alle Benutzer mehrstufige Authentifizierung für sicheren Zugriff ausführen können
- MFA für Administratorrollen erforderlich
- Aktivieren der Richtlinie zum Blockieren der Legacy Authentifizierung
