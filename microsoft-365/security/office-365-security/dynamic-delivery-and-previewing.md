---
title: Dynamische Zustellung und Vorschau mit ATP-sicheren Anlagen
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7e2da24ebac5863ab7852fdf8f9c7af8d507698b
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430351"
---
# <a name="dynamic-delivery-and-previewing-with-atp-safe-attachments"></a>Dynamische Zustellung und Vorschau mit ATP-sicheren Anlagen

## <a name="basic-features-of-dynamic-delivery"></a>Grundlegende Features der dynamischen Zustellung

"Dynamische Zustellung" ist eine Option, die für das Feature [ATP-sichere Anlagen](atp-safe-attachments.md) ausgewählt werden kann. Lesen Sie diesen Artikel, wenn Sie mehr über die Option "Dynamische Zustellung" und Funktionen für Anlagenvorschau erfahren möchten: [ATP-sichere Anlagen in Office 365](atp-safe-attachments.md).

Wenn [Richtlinien für das Feature "ATP-sichere Anlagen" für Ihre Organisation eingerichtet wurden](set-up-atp-safe-attachments-policies.md), gibt es verschiedene Optionen für die Verarbeitung von E-Mail-Anlagen, z. B. **Blockieren**, **Ersetzen** und **Dynamische Zustellung**. Je nachdem, wie Ihre Richtlinien für ATP-sichere Anlagen konfiguriert sind, kann es bei den E-Mail-Empfängern zu geringen Verzögerungen bei der Zustellung kommen, während die Anlagen gescannt werden. Um Verzögerungen zu vermeiden, wählen Sie **Dynamische Zustellung** aus.

## <a name="how-dynamic-delivery-works"></a>Funktionsweise der dynamischen Zustellung

Die Option "Dynamische Zustellung" verhindert Verzögerungen beim E-Mail-Versand, indem der Textkörper einer E-Mail-Nachricht mit einem Platzhalter für jede E-Mail-Anlage an den Empfänger übermittelt wird. Der Platzhalter bleibt, bis eine Kopie der Anlage von [ATP-sichere Anlagen](atp-safe-attachments.md) gescannt und als sicher eingestuft wurde.

- Sobald eine Anlage überprüft wurde, steht sie zum Öffnen oder Herunterladen zur Verfügung.

- Wenn eine Anlage als bösartig eingestuft wird, wird Sie an die Quarantäne gesendet, wobei eine Person im Sicherheitsteam Ihrer Organisation (beispielsweise ein globaler Administrator oder Sicherheitsadministrator) [in Office 365 isolierte Nachrichten verwalten](manage-quarantined-messages-and-files.md)kann.

Die meisten PDFs und Office-Dokumente können im sicheren Modus in der Vorschau betrachtet werden, während der ATP-Scan erfolgt. Wenn eine Anlage nicht mit der Vorschau der dynamischen Zustellung kompatibel ist, sehen E-Mail-Empfänger einen Platzhalter für die Anlage, bis der Scan von ATP-sichere Anlagen beendet ist.

> [!TIP]
> Wenn Sie ein mobiles Gerät verwenden und PDFs zunächst nicht in der dynamischen Zustellungs Vorschau gerendert werden, versuchen Sie, sich mit Ihrem mobilen Browser anzumelden.

Mit der Option "Dynamische Zustellung" können Benutzer ihre E-Mail-Nachrichten sofort lesen und beantworten, während ihre Anlagen gerade analysiert werden.

Die Überprüfung der ATP-Tresoranlagen erfolgt in derselben Region, in der sich Ihre Microsoft 365-Daten befinden. Weitere Informationen zur Geografie des Rechenzentrums finden Sie unter [Wo befinden sich Ihre Daten?](https://products.office.com/where-is-your-data-located?geo=All).

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>Was passiert, wenn jemand eine E-Mail mit einer Anlage weiterleitet?

Nehmen wir an, dass eine Organisation die Option "Dynamische Zustellung" für ihre [Richtlinie für ATP-sichere Anlagen](set-up-atp-safe-attachments-policies.md) verwendet und eine Person ein E-Mail erhält, die eine Anlagen enthält. Nehmen wir nun an, dass diese Person die E-Mail-Nachricht an jemand anderen weiterleitet. Was passiert? Dies ist davon abhängig, ob weitere Empfänger in die Richtlinien für ATP-sichere Anlagen eingeschlossen sind.

- Wenn ein Empfänger von einer Richtlinie für ATP-sichere Anlagen geschützt wird, indem die Option "Dynamische Zustellung" verwendet wird, sieht der Empfänger den Platzhalter und hat die Möglichkeit, kompatible Dateien in der Vorschau zu betrachten.

- Wird der Empfänger nicht durch eine Richtlinie für ATP-sichere Anlagen geschützt, wird die E-Mail ohne den Scan von ATP-sichere Anlagen oder Anlagenplatzhalter übermittelt.

## <a name="whats-required-for-dynamic-delivery-to-work"></a>Was ist erforderlich, damit die dynamische Zustellung funktioniert?

- Ihre Organisation muss über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen.

- Für das Feature "ATP-sichere Anlagen" müssen Richtlinien unter Verwendung der Option "Dynamische Zustellung" definiert werden. (Siehe [Einrichten von Richtlinien für ATP-sichere Anlagen in Office 365.](set-up-atp-safe-attachments-policies.md))

- Das E-Mail-System Ihrer Organisation muss in Office 365 gehostet werden. Obwohl [Office 365 Advanced Threat Protection für jeden SMTP E-Mail-Übertragungs-Agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) verwendet werden kann (z. B. Exchange Server), setzt die Option "Dynamische Zustellung" für das Feature "ATP-sichere Anlagen" voraus, dass die E-Mails Ihrer Organisation in Office 365 gehostet werden. Wenn Ihre E-Mail nicht in Office 365 gehostet wird, wählen Sie eine andere [Option für die Richtlinien für ATP-sichere Anlagen](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options) aus, z. B. **Blockieren**.

## <a name="additional-considerations"></a>Zusätzliche Überlegungen

Es gibt bestimmte Szenarien, in denen sichere Anlagen (einschließlich dynamischer Zustellung wird nicht unterstützt). Zu diesen zählen:

- E-Mail-Nachrichten in öffentlichen Ordnern.

- E-Mail-Nachrichten, die mithilfe benutzerdefinierter Regeln aus dem Postfach des Benutzers weitergeleitet werden und dann wieder zurück an dieses gesendet werden.

- E-Mail-Nachrichten, die (automatisch oder manuell) aus dem gehosteten Postfach und an andere Speicherorte verschoben werden, einschließlich Archivordnern.

- E-Mail-Nachrichten, die gelöscht werden.

- Der Post Fach Suchordner eines Benutzers, der einen Fehlerzustand aufweist.

- Umgebungen, in denen ein Exchange Online-Administrator Exclaimer aktiviert hat. Um dies zu beheben, finden Sie unter [Nachrichten mit Anlagen werden nicht zugestellt, wenn die dynamische Bereitstellung von ATP verwendet](https://support.microsoft.com/help/4014438)wird.

- Mit [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md)verschlüsselte Nachrichten).

- In Fällen, in denen die dynamische Zustellung nicht unterstützt wird, werden keine e-Mail-Nachrichten durch sichere Anlagen überprüft. Allerdings wird die Zustellung von E-Mail-Nachrichten mit Anlagen, die URLs enthalten, abhängig von der Konfiguration Ihrer [Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md) überprüft. In diesen Fällen werden URLs in E-Mail-Nachrichten und Office-Dateien überprüft.
