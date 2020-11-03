---
title: Sichere Anlagen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Administratoren können sich über das Feature "sichere Anlagen" in Microsoft Defender für Office 365 informieren.
ms.openlocfilehash: 031760c58ae18ca7dec1ecd1c1c7f870633e87fd
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844284"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Sichere Anlagen in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Sichere Anlagen in [Microsoft Defender für Office 365](office-365-atp.md) bieten eine zusätzliche Schutzschicht für e-Mail-Anlagen, die bereits durch den Schutz [vor Schadsoftware in Exchange Online Protection (EoP)](anti-malware-protection.md)überprüft wurden. Insbesondere verwendet sichere Anlagen eine virtuelle Umgebung, um Anlagen in e-Mail-Nachrichten zu überprüfen, bevor Sie an die Empfänger übermittelt werden (ein Vorgang, der als _Detonation_ bezeichnet wird).

Sicherer Anlagenschutz für e-Mail-Nachrichten wird durch Richtlinien für sichere Anlagen gesteuert. Es gibt keine Standardrichtlinie für sichere Anlagen, **daher müssen Sie eine oder mehrere Richtlinien für sichere Anlagen erstellen, um den Schutz für sichere Anlagen zu erhalten**. Anweisungen finden Sie unter [Einrichten von Richtlinien für sichere Anlagen in Defender für Office 365](set-up-atp-safe-attachments-policies.md).

In der folgenden Tabelle werden Szenarien für sichere Anlagen in Microsoft 365 und Office 365 Organisationen beschrieben, die Microsoft Defender für Office 365 enthalten (in anderen Worten: das Fehlen von Lizenzen ist in den Beispielen nie ein Problem).

****

|Szenario|Ergebnis|
|---|---|
|In der Microsoft 365 E5-Organisation von Pat sind keine Richtlinien für sichere Anlagen konfiguriert.|Pat ist nicht durch sichere Anlagen geschützt. <br/><br/> Ein Administrator muss mindestens eine Richtlinie für sichere Anlagen erstellen, damit der Schutz für sichere Anlagen aktiv ist. Darüber hinaus müssen die Bedingungen der Richtlinie Pat enthalten, wenn Pat durch sichere Anlagen geschützt werden soll.|
|Lees Organisation verfügt über eine Richtlinie für sichere Anlagen, die nur für Mitarbeiter von Finance gilt. Lee ist Mitglied der Vertriebsabteilung.|Lee ist nicht durch sichere Anlagen geschützt. <br/><br/> Finanzmitarbeiter sind durch sichere Anlagen geschützt, Vertriebsmitarbeiter (und andere Mitarbeiter) jedoch nicht.|
|Gestern hat ein Administrator in Jeans Organisation eine Richtlinie für sichere Anlagen erstellt, die für alle Mitarbeiter gilt. Bereits heute hat Jean eine e-Mail-Nachricht erhalten, die eine Anlage enthält.|Jean ist durch sichere Anlagen geschützt. <br/><br/> Normalerweise dauert es etwa 30 Minuten, bis eine neue Richtlinie wirksam wird.|
|Chris es Organisation verfügt über langjährige Richtlinien für sichere Anlagen für alle Benutzer in der Organisation. Chris erhält eine e-Mail mit einer Anlage und leitet die Nachricht dann an externe Empfänger weiter.|Chis ist durch sichere Anlagen geschützt. <br/><br/> Wenn die externen Empfänger auch Richtlinien für sichere Anlagen in Ihrer Organisation haben, unterliegen die weitergeleiteten Nachrichten diesen Richtlinien.|
|

Die Überprüfung sicherer Anlagen erfolgt in derselben Region, in der sich Ihre Microsoft 365-Daten befinden. Weitere Informationen zur Geografie des Rechenzentrums finden Sie unter [wo befinden sich Ihre Daten?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Die folgenden Features befinden sich in den globalen Einstellungen von Richtlinien für sichere Anlagen im Security & Compliance Center, diese Einstellungen sind jedoch global aktiviert oder deaktiviert und erfordern keine Richtlinien für sichere Anlagen:
>
> - [ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md).
>
> - [Sichere Dokumente in Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Richtlinieneinstellungen für sichere Anlagen

In diesem Abschnitt werden die Einstellungen in Richtlinien für sichere Anlagen beschrieben:

- **Sichere Anlagen unbekannte Malware Antwort** : Diese Einstellung steuert die Aktion für Malwarescans sicherer Anlagen in e-Mail-Nachrichten. Die verfügbaren Optionen werden in der folgenden Tabelle beschrieben:

  ****

  |Option|Effekt|Verwenden Sie Folgendes, wenn Sie möchten:|
  |---|---|---|
  |**Off**|Anlagen werden nicht durch sichere Anlagen auf Schadsoftware überprüft. Nachrichten werden weiterhin durch [Antischadsoftware-Schutz in EoP](anti-malware-protection.md)auf Schadsoftware überprüft.|Deaktivieren Sie die Überprüfung für ausgewählte Empfänger. <br/><br/> Vermeiden Sie unnötige Verzögerungen beim Weiterleiten interner e-Mails. <br/><br/> **Diese Option wird für die meisten Benutzer nicht empfohlen. Sie sollten diese Option nur verwenden, um die Überprüfung sicherer Anlagen für Empfänger zu deaktivieren, die nur Nachrichten von vertrauenswürdigen Absendern empfangen.**|
  |**Überwachen**|Sendet Nachrichten mit Anlagen und verfolgt anschließend, was mit erkannter Schadsoftware geschieht. <br/><br/> Die Zustellung sicherer Nachrichten verzögert sich möglicherweise aufgrund der Überprüfung sicherer Anlagen.|Sehen Sie, wo erkannte Schadsoftware in Ihrer Organisation vorkommt.|
  |**Blockieren**|Verhindert, dass Nachrichten mit erkannten Schadsoftware-Anlagen zugestellt werden. <br/><br/> Nachrichten werden unter [Quarantäne](manage-quarantined-messages-and-files.md) gestellt, wobei nur Administratoren (nicht Endbenutzer) die Nachrichten überprüfen, freigeben oder löschen können. <br/><br/> Blockiert automatisch zukünftige Instanzen von Nachrichten und Anlagen. <br/><br/> Die Zustellung sicherer Nachrichten verzögert sich möglicherweise aufgrund der Überprüfung sicherer Anlagen.|Schützt Ihre Organisation vor wiederholten Angriffen mit denselben Schadsoftware-Anlagen. <br/><br/> Dies ist der Standardwert und der empfohlene Wert in standardmäßigen und strengen [vordefinierten Sicherheitsrichtlinien](preset-security-policies.md).|
  |**Replace**|Entfernt erkannte Schadsoftware-Anlagen. <br/><br/> Benachrichtigt Empfänger, dass Anlagen entfernt wurden. <br/><br/>  Nachrichten werden unter [Quarantäne](manage-quarantined-messages-and-files.md) gestellt, wobei nur Administratoren (nicht Endbenutzer) die Nachrichten überprüfen, freigeben oder löschen können. <br/><br/> Die Zustellung sicherer Nachrichten verzögert sich möglicherweise aufgrund der Überprüfung sicherer Anlagen.|Erhöhen der Sichtbarkeit für Empfänger, bei denen Anlagen aufgrund von erkannter Schadsoftware entfernt wurden|
  |**Dynamische Zustellung**|Übermittelt Nachrichten sofort, ersetzt jedoch Anlagen durch Platzhalter, bis der Scan für sichere Anlagen abgeschlossen ist. <br/><br/> Ausführliche Informationen finden Sie im Abschnitt [dynamische Übermittlung in Richtlinien für sichere Anlagen](#dynamic-delivery-in-safe-attachments-policies) weiter unten in diesem Thema.|Vermeiden von Nachrichten Verzögerungen beim Schutz von Empfängern vor bösartigen Dateien <br/> <br/> Aktivieren von Empfängern zum Anzeigen einer Vorschau von Anlagen im abgesicherten Modus, während der Scan stattfindet|
  |

- **Anlage bei Erkennung umleiten: Aktivieren Sie Redirect** , und **Senden Sie die Anlage an die folgende e-Mail-Adresse** : zum **blockieren** , **überwachen** oder **ersetzen** von Nachrichten, die Schadsoftware-Anlagen enthalten, zur Analyse und Untersuchung an die angegebene interne oder externe e-Mail-Adresse senden.

  Die Empfehlung für Standard mäßige und strenge Richtlinieneinstellungen besteht darin, die Umleitung zu aktivieren. Weitere Informationen finden Sie unter [Einstellungen für sichere Anlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

- **Wenden Sie die obige Auswahl an, wenn bei der Malwareüberprüfung für Anlagen ein Timeout auftritt oder ein Fehler auftritt** : die durch **sichere Anlagen unbekannte Schadsoftware-Antwort** angegebene Aktion wird auf Nachrichten angewendet, auch wenn der sichere Anlagen Scan nicht abgeschlossen werden kann. Wählen Sie diese Option immer aus, wenn Sie **Redirect aktivieren** auswählen. Andernfalls gehen möglicherweise Nachrichten verloren.

- **Empfängerfilter** : Sie müssen die Empfängerbedingungen und Ausnahmen angeben, die bestimmen, für wen die Richtlinie gilt. Sie können die folgenden Eigenschaften für Bedingungen und Ausnahmen verwenden:

  - **Der Empfänger ist**
  - **Die Empfängerdomäne ist**
  - **Der Empfänger ist Mitglied von**

  Sie können eine Bedingung oder Ausnahme nur einmal verwenden, die Bedingung oder Ausnahme kann aber mehrere Werte enthalten. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_ ). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_ ).

- **Priorität** : Wenn Sie mehrere Richtlinien erstellen, können Sie die Reihenfolge angeben, in der Sie angewendet werden. Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

  Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Dynamische Zustellung in Richtlinien für sichere Anlagen

> [!NOTE]
> Die dynamische Zustellung funktioniert nur für Exchange Online Postfächer.

Die dynamische Zustellungs Aktion in Richtlinien für sichere Anlagen versucht, e-Mail-Zustellungsverzögerungen zu beseitigen, die möglicherweise durch das Scannen sicherer Anlagen verursacht werden Der Textkörper der e-Mail-Nachricht wird dem Empfänger mit einem Platzhalter für jede Anlage zugestellt. Der Platzhalter bleibt erhalten, bis die Anlage als sicher eingefunden wurde und dann die Anlage zum Öffnen oder Herunterladen verfügbar wird.

Wenn eine Anlage als bösartig eingefunden wird, wird die Nachricht in Quarantäne verschoben. Nur Administratoren (nicht Endbenutzer) können Nachrichten überprüfen, freigeben oder löschen, die durch Scannen sicherer Anlagen isoliert wurden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator](manage-quarantined-messages-and-files.md).

Bei den meisten PDFs und Office-Dokumenten kann im abgesicherten Modus eine Vorschau angezeigt werden, während die Überprüfung sicherer Anlagen ausgeführt wird. Wenn eine Anlage nicht mit der dynamischen Zustellungs Vorschau kompatibel ist, wird den Empfängern ein Platzhalter für die Anlage angezeigt, bis der Scan für sichere Anlagen abgeschlossen ist.

Wenn Sie ein mobiles Gerät verwenden und PDFs nicht in der dynamischen Zustellungs Vorschau auf Ihrem mobilen Gerät gerendert werden, versuchen Sie, die Nachricht in Outlook im Internet (früher als Outlook Web App bezeichnet) mit Ihrem mobilen Browser zu öffnen.

Im folgenden finden Sie einige Überlegungen zur dynamischen Zustellung und weitergeleiteten Nachrichten:

- Wenn der weitergeleitete Empfänger durch eine Richtlinie für sichere Anlagen geschützt ist, die die dynamische Zustellungsoption verwendet, sieht der Empfänger den Platzhalter, mit der Möglichkeit, eine Vorschau kompatibler Dateien anzuzeigen.

- Wenn der weitergeleitete Empfänger nicht durch eine Richtlinie für sichere Anlagen geschützt ist, werden die Nachricht und die Anlagen ohne sichere Anlagen Scans oder Anlagen Platzhalter zugestellt.

Es gibt Szenarien, in denen die dynamische Zustellung Anlagen in Nachrichten nicht ersetzen kann. Diese Szenarien umfassen:

- Nachrichten in öffentlichen Ordnern.

- Nachrichten, die mithilfe benutzerdefinierter Regeln aus dem Postfach eines Benutzers weitergeleitet werden.

- Nachrichten, die aus Cloud-Postfächern (automatisch oder manuell) an andere Speicherorte verschoben werden, einschließlich Archivordnern.

- Gelöschte Nachrichten.

- Der Post Fach Suchordner des Benutzers befindet sich in einem Fehlerzustand.

- Exchange Online Organisationen, in denen der ausrufende aktiviert ist. Um dies zu beheben, lesen Sie [KB4014438](https://support.microsoft.com/help/4014438).

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) verschlüsselte Nachrichten.

- Sie haben die dynamische Zustellungs Aktion in einer Richtlinie für sichere Anlagen konfiguriert, der Empfänger unterstützt jedoch keine dynamische Zustellung (beispielsweise ist der Empfänger ein Postfach in einer lokalen Exchange-Organisation). [Sichere Links in Microsoft Defender für Office 365](set-up-atp-safe-links-policies.md) können jedoch Office-Dateianlagen mit URLs überprüfen (je nachdem, wie die [globalen Einstellungen für sichere Links](configure-global-settings-for-safe-links.md) konfiguriert sind).

## <a name="submitting-files-for-malware-analysis"></a>Übermitteln von Dateien für die Malware Analyse

- Wenn Sie eine Datei erhalten, die Sie zur Analyse an Microsoft senden möchten, lesen Sie über [Mitteln von Schadsoftware und nicht-Schadsoftware an Microsoft zur Analyse](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).

- Wenn Sie eine e-Mail-Nachricht (mit oder ohne Anlage) erhalten, die Sie zur Analyse an Microsoft übermitteln möchten, lesen Sie [Bericht Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).
