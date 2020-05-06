---
title: Versionsvergleich für Nachrichtenverschlüsselung (OM)
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: In diesem Artikel werden die Unterschiede zwischen verschiedenen Versionen Office 365 Nachrichtenverschlüsselung erläutert.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32895f8aae8c6c23ab7f0e3d70d4caa73285fa9e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034875"
---
# <a name="compare-versions-of-ome"></a>Vergleichen von OME-Versionen

In diesem Artikel werden Legacy-Office 365 Nachrichtenverschlüsselung (OM) mit den neuen OM-Funktionen und Office 365 erweiterte Nachrichtenverschlüsselung verglichen. Die neuen Funktionen sind eine Fusion und eine neuere Version von OM und Information Rights Management (IRM). Außerdem werden eindeutige Merkmale der Bereitstellung in gcc High beschrieben. Die beiden können in Ihrer Organisation nebeneinander bestehen. Informationen zur Funktionsweise der neuen Funktionen finden Sie unter [Office 365 Message Encryption (OM)](ome.md).

||
|:-----|
|Dieser Artikel ist Teil einer größeren Reihe von Artikeln über Office 365 Nachrichtenverschlüsselung. Dieser Artikel richtet sich an Administratoren und ITPros. Wenn Sie nur auf der Suche nach Informationen zum Senden oder Empfangen einer verschlüsselten Nachricht sind, lesen Sie die Artikelliste in [Office 365 Nachrichtenverschlüsselung (OM)](ome.md) , und suchen Sie nach dem Artikel, der Ihren Anforderungen am besten entspricht. |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>Nebeneinander Vergleich von Features und Funktionen

|                                   |Alte Features       |                   |Neue Features              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**Funktion**                     | **Legacy OME**    | **IRM**           | **Neue OM-Funktionen** |
|*Senden einer verschlüsselten e-Mail*        |Durch Exchange-Nachrichtenfluss Regeln|Von Outlook Desktop oder Outlook im Internet initiierter Endbenutzer; oder über Exchange-Nachrichtenfluss Regeln|Von Outlook Desktop, Outlook für Mac oder Outlook im Internet initiierter Endbenutzer; durch Exchange-Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) und Verhinderung von Datenverlust (DLP)|
|*Vorlage für die Rechteverwaltung*       |   Nicht zutreffend      |Option und benutzerdefinierte Vorlagen nicht weiterleiten|Option "nicht weiterleiten", "nur verschlüsseln" und benutzerdefinierte Vorlagen|
|*Empfängertyp*                   |Interne und externe Empfänger|Nur interne Empfänger         |Interne und externe Empfänger|
|*Erfahrung für interne Empfänger*|Empfänger erhalten eine HTML-Nachricht, die Sie herunterladen und in einem Webbrowser oder Mobile APP öffnen.|Systemeigene Inline Erfahrung in Outlook-Clients|Systemeigene Inline Erfahrung für Empfänger in der gleichen Organisation mit Outlook-Clients.  Empfänger können die Nachricht aus dem OM-Portal mit anderen Clients als Outlook lesen (kein Download oder keine app erforderlich).|
|*Erfahrung für externen Empfänger*|Empfänger erhalten eine HTML-Nachricht, die Sie herunterladen und in einem Webbrowser oder Mobile APP öffnen.|Nicht zutreffend|Systemeigene Inline Erfahrung für Microsoft 365-Empfänger. Alle anderen Empfänger können die Nachricht aus dem OM-Portal lesen (kein Download oder keine app erforderlich).|
|*Anlagen Berechtigungen*           |Keine Einschränkungen für Anlagen|Anlagen sind geschützt|Anlagen sind für die Option "nicht weiterleiten" und benutzerdefinierte Vorlagen geschützt. Administratoren können wählen, ob Anlagen für die Option "nur verschlüsseln" geschützt sind oder nicht.|
|*Bringen Sie Ihre eigene Schlüssel Unterstützung (BYOK)*|Keine                |Keine               |BYOK unterstützt          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Vorteile der neuen OM-Funktionen über Legacy-OM

Die neuen Funktionen bieten folgende Vorteile:

- Möglichkeit der Verwendung von "nur verschlüsseln" (was eine sichere Zusammenarbeit ermöglicht), keine Weiterleitung und benutzerdefinierte Einschränkungen.
- Absender können e-Mails, die mit den neuen Funktionen verschlüsselt sind, manuell über Outlook-Desktop, Outlook für Mac und Outlook auf den Webclients senden.
- Microsoft 365-Empfänger erhalten eine Inline-Erfahrung in unterstützten Outlook-Clients verwenden. Alternativ können Administratoren entscheiden, Microsoft 365-Empfängern eine Markenerfahrung zu zeigen.
- Konten außerhalb von Microsoft 365, wie Gmail, Yahoo und Microsoft-Konten, sind mit dem OM-Portal verbunden, was eine bessere Benutzerfreundlichkeit für diese Empfänger bietet. Alle anderen Identitäten verwenden einen einmaligen Code, um auf verschlüsselte Nachrichten zuzugreifen.
- Administratoren können Branding anpassen und mehrere Branding-Vorlagen erstellen.
- Administratoren können mit den neuen Funktionen verschlüsselte e-Mails widerrufen.
- Die neuen Funktionen bieten detaillierte Nutzungsberichte über das Security &amp; Compliance Center.

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 erweiterte Nachrichten Verschlüsselungsfunktionen

Office 365 erweiterte Nachrichtenverschlüsselung bietet zusätzlich zu den neuen OM-Funktionen zusätzliche Funktionen. Sie müssen die neuen Office 365 Nachrichten Verschlüsselungsfunktionen in Ihrer Organisation eingerichtet haben, um die erweiterten Nachrichten Verschlüsselungsfunktionen nutzen zu können. Um diese Funktionen nutzen zu können, müssen Empfänger die sichere e-Mail über das OM-Portal anzeigen und darauf antworten. Die erweiterten Funktionen umfassen Folgendes:

- Nachrichten Sperrung

- Nachrichtenablauf

- Mehrere Branding-Vorlagen

Office 365 erweiterte Nachrichtenverschlüsselung wird in gcc High nicht unterstützt.

Informationen zur Verwendung der erweiterten Nachrichtenverschlüsselung finden Sie unter [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Eindeutige Merkmale Office 365 Nachrichtenverschlüsselung in einer gcc-hoch Bereitstellung

Office 365 erweiterte Nachrichtenverschlüsselung steht in einer gcc High-Umgebung nicht zur Verfügung. Sie können eine einzelne Marken Vorlage weiterhin in einer gcc-Umgebung mit hoher Qualität anpassen.

Wenn Sie Office 365 Nachrichtenverschlüsselung in einer gcc-High-Umgebung verwenden möchten, gibt es außerdem einige eindeutige Merkmale zur Empfänger Oberfläche.

### <a name="encrypted-email-from-gcc-high-to-gcc-high-recipients"></a>Verschlüsselte e-Mail von gcc-hoch an gcc-hohe Empfänger

Absender können e-Mails manuell in Outlook für PC und Mac und Outlook im Internet verschlüsseln, oder Organisationen können eine Richtlinie zum Verschlüsseln von e-Mails mithilfe von Exchange-Nachrichtenfluss Regeln einrichten.

Empfänger in gcc High erhalten dieselbe Inline Leseerfahrung in Outlook für PC und Mac sowie Outlook im Internet als alle anderen Benutzer.

### <a name="encrypted-email-from-gcc-high-to-non-gcc-high-recipients"></a>Verschlüsselte e-Mail von gcc-hoch an nicht-gcc-hohe Empfänger

Absender innerhalb von gcc High können verschlüsselte e-Mails außerhalb der gcc-Obergrenze senden.

Alle Empfänger außerhalb von gcc High, einschließlich kommerzieller Microsoft 365-Benutzer, Outlook.com-Benutzer und anderer Benutzer anderer e-Mail-Anbieter wie Gmail und Yahoo, erhalten eine Wrapper-e-Mail. Mit dieser Wrapper-e-Mail wird der Empfänger an das OM-Portal umgeleitet, in dem der Empfänger die Nachricht lesen und beantworten kann.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Koexistenz von Legacy-OM und den neuen Funktionen im gleichen Mandanten

Sie können sowohl Legacy OM als auch die neuen Funktionen im gleichen Mandanten verwenden. Als Administrator können Sie dies tun, indem Sie die Version von OM auswählen, die Sie beim Erstellen der Nachrichtenfluss Regeln verwenden möchten.

- Um die Vorgängerversion von OM anzugeben, verwenden Sie die Aktion Exchange-Nachrichtenfluss Regel **Anwenden der vorherigen Version von**om.

- Um die neuen Funktionen anzugeben, verwenden Sie die Aktion Exchange-Nachrichtenfluss Regel **anwenden Office 365 Nachrichtenverschlüsselung und Rechte Schutz**.

Benutzer können e-Mails manuell senden, die mit den neuen Funktionen aus dem Outlook-Desktop, Outlook für Mac und Outlook im Internet verschlüsselt sind.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Migrieren von Legacy-OM zu den neuen Funktionen

Auch wenn beide Versionen von OM nebeneinander bestehen können, wird dringend empfohlen, dass Sie Ihre alten Nachrichtenfluss Regeln bearbeiten, die die Regelaktion **Anwenden der vorherigen Version von OM** verwenden, um die neuen Funktionen zu verwenden. Aktualisieren Sie diese Regeln, um die Nachrichtenfluss Regelaktion **anzuwenden Office 365 Nachrichtenverschlüsselung und Rechte Schutz**. Anweisungen finden Sie unter [define Mail Flow Rules to encrypt Email Messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-ome"></a>Erste Schritte mit OM

In der Regel werden die neuen OM-Funktionen automatisch für Ihre Organisation aktiviert. Weitere Informationen zu den neuen OM-Funktionen in Ihrer Organisation finden Sie unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md).

Die Vorgängerversion von OM wird für Ihre Organisation automatisch aktiviert, wenn Sie Azure Information Protection aktiviert haben. In der Vergangenheit hat sich Legacy OM auch dann bewährt, wenn Azure Information Protection nicht aktiviert wurde. Dies ist nun nicht mehr der Fall.

Um die Verwendung von Legacy OM zu verwenden, wenn Sie Azure Information Protection aktiviert haben, konfigurieren Sie die Nachrichtenfluss Regeln, die die Regelaktion verwenden, für **die vorherige Version von OM**. Anweisungen finden Sie unter [Definieren von Nachrichtenfluss Regeln zum Verschlüsseln von e-Mail-Nachrichten](define-mail-flow-rules-to-encrypt-email.md).
