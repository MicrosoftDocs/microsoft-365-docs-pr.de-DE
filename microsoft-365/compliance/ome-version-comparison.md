---
title: Versionsvergleich der Nachrichtenverschlüsselung (Message Encryption, OME)
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: In diesem Artikel werden die Unterschiede zwischen verschiedenen Versionen von Office 365-Nachrichtenverschlüsselung.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 92beb3625c0b115fe77f1667a448bf0bf9589040
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760133"
---
# <a name="compare-versions-of-ome"></a>Vergleichen von OME-Versionen

> [!IMPORTANT]
> Am 28. Februar 2021 hat Microsoft die Unterstützung für AD RMS in Exchange Online. Wenn Sie eine Hybridumgebung bereitgestellt haben, in der Ihre Exchange-Postfächer online sind und Sie IRM mit Active Directory RMS lokal verwenden, müssen Sie zu Azure migrieren. Organisationen, die in der GCC bereitgestellt wurden, sind ebenfalls betroffen. Weitere Informationen finden Sie unter "Overview of AD RMS deprecation in Exchange Online" in diesem Artikel.

Der Rest dieses Artikels vergleicht legacy Office 365-Nachrichtenverschlüsselung (OME) mit den neuen OME-Funktionen und Office 365 Advanced Message Encryption. Die neuen Funktionen sind eine Fusion und eine neuere Version von OME und Information Rights Management (IRM). Außerdem werden eindeutige Merkmale der Bereitstellung in GCC High beschrieben. Die beiden können in Ihrer Organisation nebeneinander vorhanden sein. Informationen zur Funktionsweise der neuen Funktionen finden Sie unter [Office 365-Nachrichtenverschlüsselung (OME)](ome.md).

Dieser Artikel ist Teil einer größeren Reihe von Artikeln über Office 365-Nachrichtenverschlüsselung. Dieser Artikel richtet sich an Administratoren und ITPros. Wenn Sie nur nach Informationen zum Senden oder Empfangen einer verschlüsselten Nachricht suchen, lesen Sie die Liste der Artikel in [Office 365-Nachrichtenverschlüsselung (OME),](ome.md) und suchen Sie den Artikel, der Ihren Anforderungen am besten entspricht.

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Übersicht über die AD RMS-Veraltetkeit in Exchange Online

Exchange Online umfasst IrM-Funktionen (Information Rights Management), die Online- und Offlineschutz für E-Mail-Nachrichten und Anlagen bieten. Standardmäßig verwendet Exchange Online Azure Information Protection. Ihre Organisation hat irm jedoch möglicherweise Exchange Online für die Verwendung des lokalen Active Directory Rights Management Service (AD RMS) konfiguriert. DIE AD RMS-Unterstützung in Exchange Online in den Rente. Stattdessen ersetzt Azure Information Protection AD RMS vollständig.

Informationen dazu, ob sich diese Veraltetkeit auf Ihre Organisation aus wirkt, finden Sie unter Migrieren von AD RMS zu [Azure RMS in Exchange Online](https://support.microsoft.com/help/5001237). Dieser Artikel enthält Empfehlungen zu Migrationsoptionen.

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>Nebeneinanderer Vergleich von OME-Features und -Funktionen

|           **Situation**           | **Legacy OME**    | **IRM in AD RMS**        | **Neue OME-Funktionen** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*Senden einer verschlüsselten E-Mail*        |Über Exchange E-Mail-Flussregeln|Endbenutzer, die von Outlook desktop oder Outlook im Web initiiert werden; oder über Exchange E-Mail-Flussregeln|Endbenutzer, die von Outlook Desktop, Outlook für Mac oder Outlook im Web initiiert wurden; über Exchange E-Mail-Flussregeln (auch als Transportregeln bekannt) und Verhinderung von Datenverlust (Data Loss Prevention, DLP)|
|*Vorlage für die Rechteverwaltung*       |   Nicht zutreffend      |Option "Nicht weiterleiten" und benutzerdefinierte Vorlagen|Option "Nicht weiterleiten", "Nur verschlüsseln" und benutzerdefinierte Vorlagen|
|*Empfängertyp*                   |Interne und externe Empfänger|Nur interne Empfänger         |Interne und externe Empfänger|
|*Erfahrung für internen Empfänger*|Empfänger erhalten eine HTML-Nachricht, die sie in einem Webbrowser oder einer mobilen App herunterladen und öffnen|Native Inlineerfahrung in Outlook Clients|Native Inlineerfahrung für Empfänger in derselben Organisation, die Outlook verwenden.  Empfänger können Nachrichten aus dem OME-Portal mit anderen Clients als Outlook lesen (kein Download oder keine App erforderlich).|
|*Erfahrung für externen Empfänger*|Empfänger erhalten eine HTML-Nachricht, die sie in einem Webbrowser oder einer mobilen App herunterladen und öffnen|Nicht zutreffend|Native Inlineerfahrung für Microsoft 365 Empfänger. Alle anderen Empfänger können Nachrichten aus dem OME-Portal lesen (kein Download oder keine App erforderlich).|
|*Anlagenberechtigungen*           |Keine Einschränkungen für Anlagen|Anlagen sind geschützt|Anlagen sind für die Option Nicht weiterleiten und benutzerdefinierte Vorlagen geschützt. Administratoren können auswählen, ob Anlagen für die Option zum Verschlüsseln geschützt sind oder nicht.|
|*Bring your own key (BYOK) support*|Keine                |Keine               |BYOK unterstützt          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Vorteile der neuen OME-Funktionen gegenüber älteren OME

Die neuen Funktionen bieten die folgenden Vorteile:

- Möglichkeit zur Verwendung der Option zum Verschlüsseln (die eine sichere Zusammenarbeit ermöglicht), Option Nicht weiterleiten und benutzerdefinierte Einschränkungen.
- Absender können E-Mails, die mit den neuen Funktionen verschlüsselt wurden, manuell von Outlook Desktop, Outlook für Mac und Outlook auf den Webclients senden.
- Microsoft 365 Empfänger erhalten die Verwendung einer Inlineerfahrung in unterstützten Outlook Clients. Alternativ können Administratoren festlegen, dass Microsoft 365 eine Markenerfahrung anzeigen.
- Konten außerhalb Microsoft 365, z. B. Gmail-, Yahoo- und Microsoft-Konten, werden mit dem OME-Portal gebündelt, das eine bessere Benutzererfahrung für diese Empfänger bietet. Alle anderen Identitäten verwenden einen einmal übergebenen Code für den Zugriff auf verschlüsselte Nachrichten.
- Administratoren können branding anpassen und mehrere Brandingvorlagen erstellen.
- Administratoren können E-Mails widerrufen, die mit den neuen Funktionen verschlüsselt sind.
- Die neuen Funktionen stellen detaillierte Verwendungsberichte über das Security &amp; Compliance Center bereit.

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 Advanced Message Encryption Funktionen

Office 365 Advanced Message Encryption bietet zusätzlich zu den neuen OME-Funktionen zusätzliche Funktionen. Sie müssen die neuen Office 365-Nachrichtenverschlüsselung in Ihrer Organisation eingerichtet haben, um die Erweiterten Nachrichtenverschlüsselungsfunktionen nutzen zu können. Um diese Funktionen nutzen zu können, müssen Empfänger auch sichere E-Mails über das OME-Portal anzeigen und beantworten. Zu den erweiterten Funktionen gehören:

- Nachrichtensperrung

- Ablauf von Nachrichten

- Mehrere Brandingvorlagen

Office 365 Advanced Message Encryption wird in "High" GCC unterstützt.

Informationen zur Verwendung der erweiterten Nachrichtenverschlüsselung finden Sie [unter Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Eindeutige Merkmale von Office 365-Nachrichtenverschlüsselung in einer GCC Bereitstellung

Wenn Sie planen, Office 365-Nachrichtenverschlüsselung in einer GCC High-Umgebung zu verwenden, gibt es einige eindeutige Merkmale hinsichtlich der Empfängererfahrung.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>Verschlüsselte E-Mails zwischen GCC high und GCC High Recipients

Absender können E-Mails manuell in Outlook für PC und Mac und Outlook im Web verschlüsseln, oder Organisationen können eine Richtlinie zum Verschlüsseln von E-Mails mithilfe Exchange Nachrichtenflussregeln einrichten.

Empfänger innerhalb GCC High erhalten die gleiche Inlineleseerfahrung in Outlook für PC und Mac und Outlook im Web wie alle anderen Benutzer.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>Verschlüsselte E-Mails zwischen GCC high und Non-GCC High Recipients

Absender innerhalb GCC High können verschlüsselte E-Mails außerhalb der GCC und umgekehrt senden.

Alle Empfänger außerhalb GCC High, einschließlich kommerzieller Microsoft 365-Benutzer, Outlook.com-Benutzer und andere Benutzer anderer E-Mail-Anbieter wie Gmail und Yahoo, erhalten eine Wrapper-E-Mail. Diese Wrapper-E-Mail leitet den Empfänger an das OME-Portal weiter, in dem der Empfänger die Nachricht lesen und beantworten kann. Dies gilt auch für Absender außerhalb der GCC, die OME-verschlüsselte E-Mails an GCC senden.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Koexistenz von Legacy-OME und den neuen Funktionen im gleichen Mandanten

Sie können sowohl legacy-OME als auch die neuen Funktionen im gleichen Mandanten verwenden. Als Administrator wählen Sie dazu die Version von OME aus, die Sie verwenden möchten, wenn Sie Ihre Nachrichtenflussregeln erstellen.

- Um die Ältere Version von OME anzugeben, verwenden Sie die Exchange Nachrichtenflussregelaktion **Anwenden der vorherigen Version von OME**.

- Verwenden Sie zum Angeben der neuen Funktionen die Exchange Nachrichtenflussregelaktion **Anwenden Office 365-Nachrichtenverschlüsselung und Rechteschutz**.

Benutzer können manuell E-Mails senden, die mit den neuen Funktionen verschlüsselt sind, von Outlook Desktop, Outlook für Mac und Outlook im Web.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Migrieren von legacy OME zu den neuen Funktionen

Obwohl beide Versionen von OME nebeneinander vorhanden sein können, wird dringend empfohlen, dass Sie Ihre alten Nachrichtenflussregeln bearbeiten, die die Regelaktion Anwenden der vorherigen Version von **OME** verwenden, um die neuen Funktionen zu verwenden. Aktualisieren Sie diese Regeln, um die Nachrichtenflussregelaktion **Apply Office 365-Nachrichtenverschlüsselung rights protection zu verwenden.** Anweisungen finden Sie unter [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-ome"></a>Erste Schritte mit OME

In der Regel werden die neuen OME-Funktionen automatisch für Ihre Organisation aktiviert. Weitere Informationen zu den neuen OME-Funktionen in Ihrer Organisation finden Sie unter [Set up new Office 365-Nachrichtenverschlüsselung capabilities](set-up-new-message-encryption-capabilities.md).

Die Ältere Version von OME wird automatisch für Ihre Organisation aktiviert, wenn Sie Azure Information Protection aktiviert haben. In der Vergangenheit hat legacy OME funktioniert, auch wenn Azure Information Protection nicht aktiviert war. Dies ist nun nicht mehr der Fall.

Um mit der Verwendung von Legacy-OME zu beginnen, konfigurieren Sie, wenn Sie Azure Information Protection aktiviert haben, Nachrichtenflussregeln, die die Regelaktion Anwenden der vorherigen Version von **OME verwenden.** Anweisungen finden Sie unter [Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten.](define-mail-flow-rules-to-encrypt-email.md)