---
title: Dynamische Zustellung und Vorschau mit Office 365 sicheren ATP-Anlagen
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
description: Wenn Sie Ihre Richtlinien für ATP-sichere Anlagen einrichten, wählen Sie dynamische Zustellung aus, um Verzögerungen bei der Nachrichtenübermittlung zu vermeiden und Benutzern das Anzeigen einer Vorschau von Anlagen zu ermöglichen, die gescannt werden.
ms.openlocfilehash: 203f5082701f1f3eeea36b385918328cb85deb81
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081330"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>Dynamische Zustellung und Vorschau mit Office 365 sicheren ATP-Anlagen

## <a name="overview"></a>Übersicht

Dynamische Zustellung ist eine Option, die für ATP- [sichere Anlagen](atp-safe-attachments.md)ausgewählt werden kann. Lesen Sie diesen Artikel, um Informationen zu dynamischen Bereitstellungs-und Anlagenvorschau Funktionen in [ATP-Tresoranlagen in Office 365](atp-safe-attachments.md)zu erhalten.

Wenn für Ihre Organisation [Richtlinien für ATP-sichere Anlagen eingerichtet sind](set-up-atp-safe-attachments-policies.md) , gibt es mehrere Optionen für die Behandlung von e-Mail-Anlagen. Dazu gehören **blockieren**, **ersetzen**und **dynamische Zustellung**. Je nachdem, wie die Richtlinien für ATP-sichere Anlagen konfiguriert sind, treten e-Mail-Empfänger möglicherweise eine geringe Verzögerung bei der e-Mail-Zustellung auf, während Ihre Anlagen gescannt werden Um Nachrichten Verzögerungen zu vermeiden, wählen Sie **dynamische Zustellung**aus.
  
## <a name="how-dynamic-delivery-works"></a>Funktionsweise der dynamischen Zustellung
  
Durch dynamische Zustellung werden e-Mail-Verzögerungen vermieden, indem der Textkörper einer e-Mail-Nachricht an den Empfänger mit einem Platzhalter für jede e-Mail-Anlage gesendet wird. Der Platzhalter bleibt so lange erhalten, bis eine Kopie der Anlage überprüft und als sicher durch [ATP-sichere Anlagen](atp-safe-attachments.md)festgelegt wurde. 

- Da jede Anlage gelöscht wird, steht Sie zum Öffnen oder Herunterladen zur Verfügung. 

- Wenn eine Anlage als bösartig eingestuft wird, wird Sie an die Quarantäne gesendet, wobei eine Person im Sicherheitsteam Ihrer Organisation (beispielsweise ein Office 365 globaler Administrator oder Sicherheitsadministrator) [unter Quarantäne gestellte Nachrichten in Office 365 verwalten](manage-quarantined-messages-and-files.md)kann.

Bei den meisten PDFs und Office-Dokumenten kann im abgesicherten Modus eine Vorschau angezeigt werden, während ATP-Scans ausgeführt werden. Wenn eine Anlage nicht mit der dynamischen Zustellungs Vorschau kompatibel ist, wird e-Mail-Empfängern ein Anlagen Platzhalter angezeigt, bis die ATP-Sicherheitsanlagen Überprüfung abgeschlossen ist.

> [!TIP]
> Wenn Sie ein mobiles Gerät verwenden und PDFs zunächst nicht in der dynamischen Zustellungs Vorschau gerendert werden, versuchen Sie, sich mit Ihrem mobilen Browser bei Office 365 anzumelden.

Bei dynamischer Zustellung können Personen sofort auf Ihre e-Mail-Nachrichten lesen und Antworten, während Ihre Anlagen analysiert werden. 

Die Überprüfung der ATP-Tresoranlagen erfolgt in derselben Region, in der sich Ihre Office 365 Daten befinden. Weitere Informationen zur Geografie des Rechenzentrums finden Sie unter [wo befinden sich Ihre Daten?](https://products.office.com/where-is-your-data-located?geo=All) 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>Was passiert, wenn jemand eine e-Mail weiterleitet, die eine Anlage enthält?

Angenommen, eine Organisation verwendet dynamische Zustellungen für Ihre [Richtlinien für ATP-sichere Anlagen](set-up-atp-safe-attachments-policies.md), und jemand erhält eine e-Mail, die eine Anlage enthält. Angenommen, die Person leitet die e-Mail-Nachricht an jemand anderen weiter. Was ist los? Dies hängt davon ab, ob die zusätzlichen Empfänger in Richtlinien für ATP-sichere Anlagen enthalten sind.
  
- Wenn ein Empfänger unter Verwendung der dynamischen Zustellungsoption von einer Richtlinie für ATP-sichere Anlagen abgedeckt wird, sieht der Empfänger den Platzhalter, mit der Möglichkeit, eine Vorschau kompatibler Dateien anzuzeigen.
    
- Wenn ein Empfänger nicht von einer Richtlinie für ATP-sichere Anlagen abgedeckt wird, werden die e-Mail-Adresse und die Anlage durchlaufen, ohne ATP-Anhänge Scans oder Attachment-Platzhalter.
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>Was ist erforderlich, damit die dynamische Zustellung funktioniert?

- Ihre Organisation muss über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen.
    
- Richtlinien müssen für ATP-sichere Anlagen mithilfe der dynamischen Zustellungsoption definiert werden (siehe [Einrichten von Richtlinien für sichere ATP-Anlagen in Office 365](set-up-atp-safe-attachments-policies.md))
    
- Die e-Mail-Adresse Ihrer Organisation muss in Office 365 gehostet werden. Obwohl [Office 365 Advanced Threat Protection mit einem beliebigen SMTP-e-Mail-Übertragungs-Agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (beispielsweise Exchange Server) verwendet werden kann, erfordert die dynamische Zustellungsoption für ATP-sichere Anlagen, dass die e-Mail-Adresse Ihrer Organisation in Office 365 gehostet wird. Wenn Ihre e-Mail-Adresse nicht in Office 365 gehostet wird, wählen Sie eine andere [Richtlinienoption für ATP-sichere Anlagen](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), beispielsweise **Block**.
    
## <a name="additional-considerations"></a>Zusätzliche Überlegungen

Es gibt bestimmte Szenarien, in denen die dynamische Zustellung nicht unterstützt wird. Hierzu gehören:
  
- E-Mail-Nachrichten in öffentlichen Ordnern
    
- E-Mail-Nachrichten, die mithilfe benutzerdefinierter Regeln aus dem Postfach des Benutzers weitergeleitet werden
    
- E-Mail-Nachrichten, die (automatisch oder manuell) aus dem gehosteten Postfach und an andere Speicherorte verschoben werden, einschließlich Archivordnern
    
- Gelöschte e-Mail-Nachrichten
    
- Der Post Fach Suchordner eines Benutzers, der einen Fehlerzustand aufweist
    
- Umgebungen, in denen ein Exchange Online Administrator den ausrufenden aktiviert hat. Informationen zum Beheben dieses Problem finden Sie unter [Nachrichten mit Anlagen werden nicht zugestellt, wenn die dynamische ATP-Zustellung und der Einsatz des ausrufens verwendet werden](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery) .

- Mit [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md)verschlüsselte Nachrichten)

- In Fällen, in denen die dynamische Zustellung nicht unterstützt wird, werden keine e-Mail-Nachrichten durch ATP-sichere Anlagen überprüft. Das Übermitteln von e-Mail-Nachrichten mit Anlagen, die URLs enthalten, wird jedoch überprüft, je nachdem, wie Ihre [ATP-Richtlinien für sichere Links](set-up-atp-safe-links-policies.md) konfiguriert werden. In diesen Fällen werden URLs in e-Mail-Nachrichten und Office-Dateien überprüft.
