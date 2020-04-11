---
title: Dynamische Zustellung und Vorschau mit ATP-sichere Anlagen in Office 365.
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Beim Einrichten Ihrer Richtlinien für das Feature "ATP-sichere Anlagen", wählen Sie die Option "Dynamische Zustellung" aus, um Nachrichtenverzögerungen zu vermeiden und Personen in die Lage zu versetzen, Anlagen in der Vorschau zu betrachten, die gescannt werden.
ms.openlocfilehash: 755a5a317710946a3a03004482a6b48c8947c1a7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599422"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>Dynamische Zustellung und Vorschau mit ATP-sichere Anlagen in Office 365.

## <a name="overview"></a>Übersicht

"Dynamische Zustellung" ist eine Option, die für das Feature [ATP-sichere Anlagen](atp-safe-attachments.md) ausgewählt werden kann. Lesen Sie diesen Artikel, wenn Sie mehr über die Option "Dynamische Zustellung" und Funktionen für Anlagenvorschau erfahren möchten: [ATP-sichere Anlagen in Office 365](atp-safe-attachments.md).

Wenn [Richtlinien für das Feature "ATP-sichere Anlagen" für Ihre Organisation eingerichtet wurden](set-up-atp-safe-attachments-policies.md), gibt es verschiedene Optionen für die Verarbeitung von E-Mail-Anlagen, z. B. **Blockieren**, **Ersetzen** und **Dynamische Zustellung**. Je nachdem, wie Ihre Richtlinien für ATP-sichere Anlagen konfiguriert sind, kann es bei den E-Mail-Empfängern zu geringen Verzögerungen bei der Zustellung kommen, während die Anlagen gescannt werden. Um Verzögerungen zu vermeiden, wählen Sie **Dynamische Zustellung** aus.

## <a name="how-dynamic-delivery-works"></a>Funktionsweise der dynamischen Zustellung

Die Option "Dynamische Zustellung" verhindert Verzögerungen beim E-Mail-Versand, indem der Textkörper einer E-Mail-Nachricht mit einem Platzhalter für jede E-Mail-Anlage an den Empfänger übermittelt wird. Der Platzhalter bleibt, bis eine Kopie der Anlage von [ATP-sichere Anlagen](atp-safe-attachments.md) gescannt und als sicher eingestuft wurde.

- Sobald eine Anlage überprüft wurde, steht sie zum Öffnen oder Herunterladen zur Verfügung.

- Wird eine Anlage als böswillig identifiziert, wird sie in Quarantäne gestellt. Ein Mitglied des Sicherheitsteams Ihrer Organisation (z. B. ein globaler Office 365-Administrator oder ein Sicherheitsadministrator) kann [in Quarantäne befindliche Nachrichten in Office 365 verwalten](manage-quarantined-messages-and-files.md).

Die meisten PDFs und Office-Dokumente können im sicheren Modus in der Vorschau betrachtet werden, während der ATP-Scan erfolgt. Wenn eine Anlage nicht mit der Vorschau der dynamischen Zustellung kompatibel ist, sehen E-Mail-Empfänger einen Platzhalter für die Anlage, bis der Scan von ATP-sichere Anlagen beendet ist.

> [!TIP]
> Wenn Sie ein mobiles Gerät verwenden und PDFs in der Vorschau für "Dynamische Zustellung" zunächst nicht gerendert werden, versuchen Sie es, indem Sie sich mit Ihrem mobilen Browser bei Office 365 anmelden.

Mit der Option "Dynamische Zustellung" können Benutzer ihre E-Mail-Nachrichten sofort lesen und beantworten, während ihre Anlagen gerade analysiert werden.

Das Scannen durch das Feature "ATP-sichere Anlagen" erfolgt in der gleichen Region, in der sich Ihre Office 365-Daten befinden. Weitere Informationen zur Geografie des Rechenzentrums finden Sie unter [Wo befinden sich Ihre Daten?](https://products.office.com/where-is-your-data-located?geo=All).

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>Was passiert, wenn jemand eine E-Mail mit einer Anlage weiterleitet?

Nehmen wir an, dass eine Organisation die Option "Dynamische Zustellung" für ihre [Richtlinie für ATP-sichere Anlagen](set-up-atp-safe-attachments-policies.md) verwendet und eine Person ein E-Mail erhält, die eine Anlagen enthält. Nehmen wir nun an, dass diese Person die E-Mail-Nachricht an jemand anderen weiterleitet. Was passiert? Dies ist davon abhängig, ob weitere Empfänger in die Richtlinien für ATP-sichere Anlagen eingeschlossen sind.

- Wenn ein Empfänger von einer Richtlinie für ATP-sichere Anlagen geschützt wird, indem die Option "Dynamische Zustellung" verwendet wird, sieht der Empfänger den Platzhalter und hat die Möglichkeit, kompatible Dateien in der Vorschau zu betrachten.

- Wird der Empfänger nicht durch eine Richtlinie für ATP-sichere Anlagen geschützt, wird die E-Mail ohne den Scan von ATP-sichere Anlagen oder Anlagenplatzhalter übermittelt.

## <a name="whats-required-for-dynamic-delivery-to-work"></a>Was ist erforderlich, damit die dynamische Zustellung funktioniert?

- Ihre Organisation muss über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen.

- Für das Feature "ATP-sichere Anlagen" müssen Richtlinien unter Verwendung der Option "Dynamische Zustellung" definiert werden. (Siehe [Einrichten von Richtlinien für ATP-sichere Anlagen in Office 365.](set-up-atp-safe-attachments-policies.md))

- Das E-Mail-System Ihrer Organisation muss in Office 365 gehostet werden. Obwohl [Office 365 Advanced Threat Protection für jeden SMTP E-Mail-Übertragungs-Agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) verwendet werden kann (z. B. Exchange Server), setzt die Option "Dynamische Zustellung" für das Feature "ATP-sichere Anlagen" voraus, dass die E-Mails Ihrer Organisation in Office 365 gehostet werden. Wenn Ihre E-Mail nicht in Office 365 gehostet wird, wählen Sie eine andere [Option für die Richtlinien für ATP-sichere Anlagen](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options) aus, z. B. **Blockieren**.

## <a name="additional-considerations"></a>Zusätzliche Überlegungen

Es gibt bestimmte Szenarien, in denen die dynamische Zustellung nicht unterstützt wird. Hierzu gehören:

- E-Mail-Nachrichten befinden sich in öffentlichen Ordnern

- E-Mail-Nachrichten werden über benutzerdefinierte Regeln auswärts und dann zurück in das Postfach geroutet

- E-Mail-Nachrichten werden (automatisch oder manuell) aus dem gehosteten Postfach an andere Speicherorte einschließlich Archivordner verschoben

- Gelöschte E-Mail-Nachrichten

- Der Suchordner im Postfach eines Benutzers befindet sich im Status "Fehler"

- Umgebungen, in denen ein Exchange Online-Administrator Exclaimer aktiviert hat. Um dieses Problem zu beheben, ziehen Sie [Nachrichten mit Anlagen werden nicht zugestellt, wenn die ATP-Option "Dynamische Zustellung" und Exclaimer verwendet werden](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery) zurate.

- Mit [S/MIME (Secure/Multipurpose Internet Mail Extensions)](s-mime-for-message-signing-and-encryption.md) verschlüsselte Nachrichten

- In Fällen, in denen die dynamische Zustellung nicht unterstützt wird, werden E-Mail-Nachrichten nicht durch das Feature "ATP-sichere Anlagen" gescannt. Allerdings wird die Zustellung von E-Mail-Nachrichten mit Anlagen, die URLs enthalten, abhängig von der Konfiguration Ihrer [Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md) überprüft. In diesen Fällen werden URLs in E-Mail-Nachrichten und Office-Dateien überprüft.
