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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Administratoren können sich über das Feature "Sichere Anlagen" in Microsoft Defender for Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab3fd89c02186dfbdb6c9a3d754a4902d8b945f8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246380"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Sichere Anlagen in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Sichere Anlagen in [Microsoft Defender for Office 365](defender-for-office-365.md) bietet eine zusätzliche Schutzebene für E-Mail-Anlagen, die bereits vom Schutz vor Schadsoftware [in Exchange Online Protection (EOP)](anti-malware-protection.md)überprüft wurden. Insbesondere sichere Anlagen verwenden eine virtuelle Umgebung, um Anlagen in E-Mail-Nachrichten zu überprüfen, bevor sie an Empfänger übermittelt werden (ein Prozess, der als _Detonation bekannt ist)._

Der Schutz sicherer Anlagen für E-Mail-Nachrichten wird durch Richtlinien für sichere Anlagen gesteuert. Es gibt keine Standardrichtlinie für sichere Anlagen. Um den Schutz sicherer Anlagen zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere **Anlagen erstellen.** Anweisungen finden Sie [unter Set up Safe Attachments policies in Defender for Office 365](set-up-safe-attachments-policies.md).

In der folgenden Tabelle werden Szenarien für sichere Anlagen in Microsoft 365- und Office 365-Organisationen beschrieben, zu denen Microsoft Defender für Office 365 gehört (d. h. fehlende Lizenzierung ist in den Beispielen nie ein Problem).

<br>

****

|Szenario|Ergebnis|
|---|---|
|In der Microsoft 365 E5 von Pat sind keine Richtlinien für sichere Anlagen konfiguriert.|Pat ist nicht durch sichere Anlagen geschützt. <p> Ein Administrator muss mindestens eine Richtlinie für sichere Anlagen erstellen, damit der Schutz sicherer Anlagen aktiv ist. Darüber hinaus müssen die Bedingungen der Richtlinie Pat enthalten, wenn Pat durch sichere Anlagen geschützt werden soll.|
|Lees Organisation verfügt über eine Richtlinie für sichere Anlagen, die nur für Finanzmitarbeiter gilt. Lee ist Mitglied der Vertriebsabteilung.|Lee ist nicht durch sichere Anlagen geschützt. <p> Finanzmitarbeiter sind durch sichere Anlagen geschützt, Vertriebsmitarbeiter (und andere Mitarbeiter) dagegen nicht.|
|Gestern hat ein Administrator in Der Organisation von Jean eine Richtlinie für sichere Anlagen erstellt, die für alle Mitarbeiter gilt. Zuvor hat Er eine E-Mail-Nachricht mit einer Anlage erhalten.|"Jean" ist durch sichere Anlagen geschützt. <p> In der Regel dauert es etwa 30 Minuten, bis eine neue Richtlinie wirksam wird.|
|Chris' Organisation verfügt über langfristige Richtlinien für sichere Anlagen für alle in der Organisation. Chris empfängt eine E-Mail mit einer Anlage und gibt die Nachricht dann an externe Empfänger weiter.|Chis ist durch sichere Anlagen geschützt. <p> Wenn die externen Empfänger auch Richtlinien für sichere Anlagen in ihrer Organisation haben, unterliegen die weitergeleiteten Nachrichten diesen Richtlinien.|
|

Die Überprüfung sicherer Anlagen erfolgt in derselben Region, in der sich Microsoft 365 befinden. Weitere Informationen zur Geografie des Rechenzentrums finden Sie unter [Wo befinden sich Ihre Daten?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Die folgenden Features befinden sich in den globalen Einstellungen von Richtlinien für sichere Anlagen im Security & Compliance Center. Diese Einstellungen sind jedoch global aktiviert oder deaktiviert und erfordern keine Richtlinien für sichere Anlagen:
>
> - [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md).
> - [Sichere Dokumente in Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Richtlinieneinstellungen für sichere Anlagen

In diesem Abschnitt werden die Einstellungen in Richtlinien für sichere Anlagen beschrieben:

- **Antwort auf unbekannte Schadsoftware** für sichere Anlagen: Diese Einstellung steuert die Aktion zum Scannen von Schadsoftware sicherer Anlagen in E-Mail-Nachrichten. Die verfügbaren Optionen werden in der folgenden Tabelle beschrieben:

  <br>

  ****

  |Option|Effekt|Verwenden Sie, wenn Sie:|
  |---|---|---|
  |**Off**|Anlagen werden nicht von sicheren Anlagen auf Schadsoftware überprüft. Nachrichten werden weiterhin durch Den Schutz vor Schadsoftware [in EOP auf Schadsoftware überprüft.](anti-malware-protection.md)|Deaktivieren sie die Überprüfung für ausgewählte Empfänger. <p> Vermeiden Sie unnötige Verzögerungen beim Routing interner E-Mails. <p> **Diese Option wird für die meisten Benutzer nicht empfohlen. Sie sollten diese Option nur verwenden, um die Überprüfung sicherer Anlagen für Empfänger zu deaktivieren, die nur Nachrichten von vertrauenswürdigen Absendern empfangen.**|
  |**Überwachen**|Liefert Nachrichten mit Anlagen und verfolgt dann, was mit erkannter Schadsoftware geschieht. <p> Die Zustellung sicherer Nachrichten kann aufgrund der Überprüfung sicherer Anlagen verzögert werden.|Sehen Sie, wo erkannte Schadsoftware in Ihrer Organisation liegt.|
  |**Blockieren**|Verhindert, dass Nachrichten mit erkannten Schadsoftwareanlagen zugestellt werden. <p> Nachrichten werden [isoliert,](manage-quarantined-messages-and-files.md) wenn nur Administratoren (nicht Endbenutzer) die Nachrichten überprüfen, veröffentlichen oder löschen können. <p> Blockiert automatisch zukünftige Instanzen der Nachrichten und Anlagen. <p> Die Zustellung sicherer Nachrichten kann aufgrund der Überprüfung sicherer Anlagen verzögert werden.|Schützt Ihre Organisation vor wiederholten Angriffen mit denselben Schadsoftwareanlagen. <p> Dies ist der Standardwert und der empfohlene Wert in standard und Strict [voreingestellte Sicherheitsrichtlinien](preset-security-policies.md).|
  |**Replace**|Entfernt erkannte Schadsoftwareanlagen. <p> Benachrichtigt Empfänger, dass Anlagen entfernt wurden. <p>  Nachrichten werden [isoliert,](manage-quarantined-messages-and-files.md) wenn nur Administratoren (nicht Endbenutzer) die Nachrichten überprüfen, veröffentlichen oder löschen können. <p> Die Zustellung sicherer Nachrichten kann aufgrund der Überprüfung sicherer Anlagen verzögert werden.|Erhöhen Sie die Sichtbarkeit für Empfänger, dass Anlagen aufgrund erkannter Schadsoftware entfernt wurden.|
  |**Dynamische Übermittlung**|Übermittelt Nachrichten sofort, ersetzt anlagen jedoch durch Platzhalter, bis die Überprüfung sicherer Anlagen abgeschlossen ist. <p> Weitere Informationen finden Sie im Abschnitt Richtlinien für die dynamische [Zustellung in](#dynamic-delivery-in-safe-attachments-policies) sicheren Anlagen weiter weiter weiter in diesem Artikel.|Vermeiden Von Nachrichtenverzögerungen beim Schutz von Empfängern vor schädlichen Dateien. <p> Ermöglichen Sie Empfängern die Vorschau von Anlagen im abgesicherten Modus, während die Überprüfung stattfindet.|
  |

- Umleitungsanlage bei **Erkennung:** Aktivieren Sie die Umleitung, und senden Sie die Anlage an die folgende E-Mail-Adresse: Senden Sie für Block **-,** **Monitor-** oder **Replace-Aktionen** Nachrichten, die Schadsoftwareanlagen enthalten, zur Analyse und Untersuchung an die angegebene interne oder externe E-Mail-Adresse.

  Die Empfehlung für Standard- und Strict-Richtlinieneinstellungen besteht in der Aktivierung der Umleitung. Weitere Informationen finden Sie unter [Einstellungen für sichere Anlagen](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

- **Wenden Sie die oben** aufgeführte Auswahl an, wenn die  Schadsoftwareprüfung auf Anlagen ein Zeit- oder Fehlerfehler auftritt: Die durch die unbekannte Schadsoftwareantwort für sichere Anlagen angegebene Aktion wird für Nachrichten ausgeführt, auch wenn die Überprüfung sicherer Anlagen nicht abgeschlossen werden kann. Wählen Sie diese Option immer aus, wenn Sie **Umleitung aktivieren auswählen.** Andernfalls gehen Nachrichten möglicherweise verloren.

- **Empfängerfilter:** Sie müssen die Empfängerbedingungen und Ausnahmen angeben, die bestimmen, auf wen die Richtlinie angewendet wird. Sie können die folgenden Eigenschaften für Bedingungen und Ausnahmen verwenden:
  - **Der Empfänger ist**
  - **Die Empfängerdomäne ist**
  - **Der Empfänger ist Mitglied von**

  Sie können eine Bedingung oder Ausnahme nur einmal verwenden, die Bedingung oder Ausnahme kann aber mehrere Werte enthalten. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

- **Priorität:** Wenn Sie mehrere Richtlinien erstellen, können Sie die Reihenfolge angeben, in der sie angewendet werden. Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

  Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Dynamische Übermittlung in Richtlinien für sichere Anlagen

> [!NOTE]
> Die dynamische Zustellung funktioniert nur für Exchange Online Postfächer.

Die Dynamische Zustellungsaktion in Richtlinien für sichere Anlagen versucht, Verzögerungen bei der E-Mail-Zustellung zu vermeiden, die durch die Überprüfung sicherer Anlagen verursacht werden können. Der Textkörper der E-Mail-Nachricht wird dem Empfänger mit einem Platzhalter für jede Anlage zugestellt. Der Platzhalter bleibt erhalten, bis die Anlage als sicher eingestuft wird, und dann steht die Anlage zum Öffnen oder Herunterladen zur Verfügung.

Wenn eine Anlage als schädlich festgestellt wird, wird die Nachricht in Quarantäne gestellt. Nur Administratoren (nicht Endbenutzer) können Nachrichten überprüfen, veröffentlichen oder löschen, die von der Überprüfung sicherer Anlagen isoliert wurden. Weitere Informationen finden Sie unter [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).

Die meisten PDFs und Office können im abgesicherten Modus in der Vorschau angezeigt werden, während die Überprüfung sicherer Anlagen ausgeführt wird. Wenn eine Anlage nicht mit der Vorschau für dynamische Übermittlung kompatibel ist, wird den Empfängern ein Platzhalter für die Anlage angezeigt, bis die Überprüfung sicherer Anlagen abgeschlossen ist.

Wenn Sie ein mobiles Gerät verwenden und PDFs nicht im Vorschaufenster für die dynamische Übermittlung auf Ihrem mobilen Gerät gerendert werden, versuchen Sie, die Nachricht in Outlook im Web (früher als Outlook Web App bezeichnet) mit Ihrem mobilen Browser zu öffnen.

Hier sind einige Überlegungen zur dynamischen Übermittlung und weitergeleiteten Nachrichten:

- Wenn der weitergeleitete Empfänger durch eine Richtlinie für sichere Anlagen geschützt ist, die die Option Dynamische Übermittlung verwendet, wird dem Empfänger der Platzhalter mit der Möglichkeit angezeigt, eine Vorschau kompatibler Dateien anzuzeigen.
- Wenn der weitergeleitete Empfänger nicht durch eine Richtlinie für sichere Anlagen geschützt ist, werden die Nachricht und Anlagen ohne Überprüfung durch sichere Anlagen oder Anlagenplatzhalter zugestellt.

Es gibt Szenarien, in denen die dynamische Übermittlung Anlagen in Nachrichten nicht ersetzen kann. Diese Szenarien umfassen:

- Nachrichten in öffentlichen Ordnern.
- Nachrichten, die mithilfe von benutzerdefinierten Regeln aus und dann wieder in das Postfach eines Benutzers geroutet werden.
- Nachrichten, die (automatisch oder manuell) aus Cloudpostfächern an andere Speicherorte verschoben werden, einschließlich Archivordnern.
- Posteingangsregeln verschieben die Nachricht aus dem Posteingang in einen anderen Ordner.
- Gelöschte Nachrichten.
- Der Postfachsuchordner des Benutzers befindet sich im Fehlerstatus.
- Exchange Online Organisationen, in denen Exclaimer aktiviert ist. Informationen zum Beheben dieses Problems finden Sie unter [KB4014438](https://support.microsoft.com/help/4014438).
- [S/MIME)](s-mime-for-message-signing-and-encryption.md) verschlüsselte Nachrichten.
- Sie haben die Dynamische Zustellungsaktion in einer Richtlinie für sichere Anlagen konfiguriert, der Empfänger unterstützt jedoch keine dynamische Zustellung (z. B. ist der Empfänger ein Postfach in einer lokalen Exchange Organisation). Sichere Links [in Microsoft Defender for Office 365](set-up-safe-links-policies.md) können jedoch Office Dateianlagen überprüfen, die URLs [](configure-global-settings-for-safe-links.md) enthalten (je nachdem, wie die globalen Einstellungen für sichere Links konfiguriert sind).

## <a name="submitting-files-for-malware-analysis"></a>Übermitteln von Dateien für die Schadsoftwareanalyse

- Wenn Sie eine Datei erhalten, die Sie zur Analyse an Microsoft senden möchten, finden Sie unter [Submit malware and non-malware to Microsoft for analysis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).
- Wenn Sie eine E-Mail-Nachricht (mit oder ohne Anlage) erhalten, die Sie zur Analyse an Microsoft übermitteln möchten, lesen Sie Melden von Nachrichten und Dateien [an Microsoft](report-junk-email-messages-to-microsoft.md).
