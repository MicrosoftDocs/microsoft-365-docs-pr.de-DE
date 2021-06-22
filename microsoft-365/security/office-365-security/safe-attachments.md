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
description: Administratoren können sich über das Feature Tresor Anlagen in Microsoft Defender für Office 365 informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 127d862d235abc4cd81f62679b97077c7a80bd70
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054395"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Tresor Anlagen in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Tresor Anlagen in [Microsoft Defender für Office 365](defender-for-office-365.md) bietet eine zusätzliche Schutzebene für E-Mail-Anlagen, die bereits von [Anti-Malware-Schutz in Exchange Online Protection (EOP)](anti-malware-protection.md)gescannt wurden. Insbesondere verwendet Tresor Anlagen eine virtuelle Umgebung, um Anlagen in E-Mail-Nachrichten zu überprüfen, bevor sie an Empfänger übermittelt werden (ein Prozess, der als _Detonation_ bezeichnet wird).

Tresor Der Anlagenschutz für E-Mail-Nachrichten wird durch Tresor Anlagenrichtlinien gesteuert. Es gibt keine Standardrichtlinie Tresor Anlagen. **Um den Schutz von Tresor Anlagen zu erhalten, müssen Sie eine oder mehrere Tresor Anlagenrichtlinien erstellen.** Anweisungen finden Sie unter [Einrichten Tresor Anlagenrichtlinien in Defender für Office 365](set-up-safe-attachments-policies.md).

In der folgenden Tabelle werden Szenarien für Tresor Anlagen in Microsoft 365 und Office 365 Organisationen beschrieben, die Microsoft Defender für Office 365 enthalten (d. h. fehlende Lizenzierung ist in den Beispielen nie ein Problem).

<br>

****

|Szenario|Ergebnis|
|---|---|
|Pats Microsoft 365 E5 Organisation hat keine Tresor Anlagenrichtlinien konfiguriert.|Pat ist nicht durch Tresor Anlagen geschützt. <p> Ein Administrator muss mindestens eine Tresor Anlagenrichtlinie erstellen, damit Tresor Anlagenschutz aktiv ist. Darüber hinaus müssen die Bedingungen der Richtlinie Pat enthalten, wenn Pat durch Tresor Anlagen geschützt werden soll.|
|Lees Organisation verfügt über eine richtlinie für Tresor Anlagen, die nur für Mitarbeiter im Finanzbereich gilt. Lee ist Mitglied der Vertriebsabteilung.|Lee ist nicht durch Tresor Anlagen geschützt. <p> Finanzmitarbeiter werden durch Tresor Anlagen geschützt, Vertriebsmitarbeiter (und andere Mitarbeiter) jedoch nicht.|
|Im gestrigen Tag hat ein Administrator in Der Organisation von Einerz eine richtlinie für Tresor Anlagen erstellt, die für alle Mitarbeiter gilt. Früher, heute, hat Einer eine E-Mail-Nachricht erhalten, die eine Anlage enthielt.|Aufer ist durch Tresor Anlagen geschützt. <p> In der Regel dauert es ca. 30 Minuten, bis eine neue Richtlinie wirksam wird.|
|Chriss Organisation verfügt über lange Tresor Anlagenrichtlinien für alle Personen in der Organisation. Chris empfängt eine E-Mail mit einer Anlage und leitet die Nachricht dann an externe Empfänger weiter.|Chis ist durch Tresor Anlagen geschützt. <p> Wenn die externen Empfänger auch über Tresor Anlagenrichtlinien in ihrer Organisation verfügen, unterliegen die weitergeleiteten Nachrichten diesen Richtlinien.|
|

Tresor Die Anlagenüberprüfung erfolgt in derselben Region, in der sich Ihre Microsoft 365-Daten befinden. Weitere Informationen zur Geografie von Rechenzentren finden Sie unter ["Wo befinden sich Ihre Daten?"](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Die folgenden Features befinden sich in den globalen Einstellungen Tresor Anlagenrichtlinien im Microsoft 365 Defender Portal. Diese Einstellungen sind jedoch global aktiviert oder deaktiviert und erfordern keine Tresor Anlagenrichtlinien:
>
> - [Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md).
> - [Sichere Dokumente in Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Tresor Richtlinieneinstellungen für Anlagen

In diesem Abschnitt werden die Einstellungen in Tresor Anlagenrichtlinien beschrieben:

- **Tresor Attachments unknown malware response:** This setting controls the action for Tresor Attachments malware scanning in email messages. Die verfügbaren Optionen werden in der folgenden Tabelle beschrieben:

  <br>

  ****

  |Option|Effekt|Verwenden Sie folgende Zwecke:|
  |---|---|---|
  |**Aus**|Anlagen werden von Tresor Anlagen nicht auf Schadsoftware gescannt. Nachrichten werden weiterhin durch [Antischadsoftwareschutz in EOP](anti-malware-protection.md)auf Schadsoftware überprüft.|Deaktivieren Sie die Überprüfung für ausgewählte Empfänger. <p> Vermeiden Sie unnötige Verzögerungen beim Weiterleiten interner E-Mails. <p> **Diese Option wird für die meisten Benutzer nicht empfohlen. Sie sollten diese Option nur verwenden, um Tresor Anlagenüberprüfung für Empfänger zu deaktivieren, die nur Nachrichten von vertrauenswürdigen Absendern empfangen.**|
  |**Überwachen**|Übermittelt Nachrichten mit Anlagen und verfolgt dann, was mit erkannter Schadsoftware geschieht. <p> Die Zustellung von sicheren Nachrichten kann aufgrund Tresor Anlagenüberprüfung verzögert werden.|Sehen Sie, wo erkannte Schadsoftware in Ihrer Organisation vorkommt.|
  |**Blockieren**|Verhindert, dass Nachrichten mit erkannten Schadsoftwareanlagen zugestellt werden. <p> Nachrichten werden [in Quarantäne gestellt,](manage-quarantined-messages-and-files.md) wo nur Administratoren (keine Benutzer) die Nachrichten überprüfen, freigeben oder löschen können. <p> Blockiert automatisch zukünftige Instanzen der Nachrichten und Anlagen. <p> Die Zustellung von sicheren Nachrichten kann aufgrund Tresor Anlagenüberprüfung verzögert werden.|Schützt Ihre Organisation vor wiederholten Angriffen mit denselben Schadsoftwareanlagen. <p> Dies ist der Standardwert und der empfohlene Wert in [voreingestellten Standard- und Strict-Sicherheitsrichtlinien.](preset-security-policies.md)|
  |**Replace**|Entfernt erkannte Schadsoftwareanlagen. <p> Benachrichtigt Empfänger, dass Anlagen entfernt wurden. <p>  Nachrichten werden [in Quarantäne gestellt,](manage-quarantined-messages-and-files.md) wo nur Administratoren (keine Benutzer) die Nachrichten überprüfen, freigeben oder löschen können. <p> Die Zustellung von sicheren Nachrichten kann aufgrund Tresor Anlagenüberprüfung verzögert werden.|Erhöhen Sie die Sichtbarkeit für Empfänger, dass Anlagen aufgrund erkannter Schadsoftware entfernt wurden.|
  |**Dynamische Zustellung**|Übermittelt Nachrichten sofort, ersetzt Anlagen jedoch durch Platzhalter, bis Tresor Überprüfung der Anlagen abgeschlossen ist. <p> Ausführliche Informationen finden Sie im Abschnitt ["Dynamische Zustellung in Tresor Anlagenrichtlinien"](#dynamic-delivery-in-safe-attachments-policies) weiter unten in diesem Artikel.|Vermeiden Sie Nachrichtenverzögerungen, während Empfänger vor schädlichen Dateien geschützt werden. <p> Ermöglichen Sie Empfängern die Vorschau von Anlagen im abgesicherten Modus, während die Überprüfung stattfindet.|
  |

- **Anlage bei Erkennung umleiten: Aktivieren Sie die Umleitung** und senden Sie die Anlage an die folgende **E-Mail-Adresse:** Für **Blockierungs-,** **Monitor-** oder **Ersetzungsaktionen** senden Sie Nachrichten, die Schadsoftwareanlagen enthalten, an die angegebene interne oder externe E-Mail-Adresse zur Analyse und Untersuchung.

  Die Empfehlung für Standard- und Strict-Richtlinieneinstellungen besteht darin, die Umleitung zu aktivieren. Weitere Informationen finden Sie unter [Tresor Anlageneinstellungen.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- **Wenden Sie die oben genannte Auswahl an, wenn bei der Schadsoftwareüberprüfung nach Anlagen ein Zeitüberschreitung auftritt oder ein Fehler auftritt:** Die durch **Tresor Attachments unknown malware response** angegebene Aktion wird auf Nachrichten angewendet, auch wenn Tresor Attachments-Überprüfung nicht abgeschlossen werden kann. Wählen Sie immer diese Option aus, wenn Sie **"Umleitung aktivieren"** auswählen. Andernfalls können Nachrichten verloren gegangen sein.

- **Empfängerfilter:** Sie müssen die Empfängerbedingungen und -ausnahmen angeben, die bestimmen, für wen die Richtlinie gilt. Sie können die folgenden Eigenschaften für Bedingungen und Ausnahmen verwenden:
  - **Der Empfänger ist**
  - **Die Empfängerdomäne ist**
  - **Der Empfänger ist Mitglied von**

  Sie können eine Bedingung oder Ausnahme nur einmal verwenden, die Bedingung oder Ausnahme kann aber mehrere Werte enthalten. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

- **Priorität:** Wenn Sie mehrere Richtlinien erstellen, können Sie die Reihenfolge angeben, in der sie angewendet werden. Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

  Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Dynamische Zustellung in Tresor Anlagenrichtlinien

> [!NOTE]
> Die dynamische Zustellung funktioniert nur für Exchange Online Postfächer.

Die Aktion "Dynamische Zustellung" in Tresor Anlagenrichtlinien zielt darauf ab, verzögerungen bei der E-Mail-Zustellung zu vermeiden, die durch Tresor Anlagenüberprüfung verursacht werden können. Der Text der E-Mail-Nachricht wird mit einem Platzhalter für jede Anlage an den Empfänger übermittelt. Der Platzhalter bleibt, bis die Anlage als sicher eingestuft wurde, und dann steht die Anlage zum Öffnen oder Herunterladen zur Verfügung.

Wenn festgestellt wird, dass eine Anlage bösartig ist, wird die Nachricht unter Quarantäne gestellt. Nur Administratoren (nicht Benutzer) können Nachrichten, die durch Tresor Anlagenüberprüfung unter Quarantäne gestellt wurden, überprüfen, freigeben oder löschen. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator.](manage-quarantined-messages-and-files.md)

Die meisten PDFs und Office Dokumente können im abgesicherten Modus in der Vorschau angezeigt werden, während Tresor Attachments-Überprüfung ausgeführt wird. Wenn eine Anlage nicht mit dem Vorschauprogramm für die dynamische Zustellung kompatibel ist, wird den Empfängern ein Platzhalter für die Anlage angezeigt, bis Tresor Attachments-Überprüfung abgeschlossen ist.

Wenn Sie ein mobiles Gerät verwenden und PDFs nicht im Vorschauprogramm für die dynamische Zustellung auf Ihrem mobilen Gerät gerendert werden, versuchen Sie, die Nachricht über Ihren mobilen Browser in Outlook im Web (früher als Outlook Web App bezeichnet) zu öffnen.

Hier sind einige Überlegungen für die dynamische Zustellung und weitergeleitete Nachrichten:

- Wenn der weitergeleitete Empfänger durch eine Tresor Anlagenrichtlinie geschützt ist, die die Option "Dynamische Zustellung" verwendet, sieht der Empfänger den Platzhalter mit der Möglichkeit, eine Vorschau kompatibler Dateien anzuzeigen.
- Wenn der weitergeleitete Empfänger nicht durch eine Tresor Attachments-Richtlinie geschützt ist, werden die Nachricht und Anlagen ohne Tresor Anlagenüberprüfung oder Anlagenplatzhalter übermittelt.

Es gibt Szenarien, in denen die dynamische Zustellung Anlagen in Nachrichten nicht ersetzen kann. Diese Szenarien umfassen:

- Nachrichten in öffentlichen Ordnern.
- Nachrichten, die mithilfe von benutzerdefinierten Regeln aus dem Postfach eines Benutzers und dann zurück in das Postfach eines Benutzers geleitet werden.
- Nachrichten, die (automatisch oder manuell) aus Cloudpostfächern an andere Speicherorte, einschließlich Archivordner, verschoben werden.
- Posteingangsregeln verschieben die Nachricht aus dem Posteingang in einen anderen Ordner.
- Gelöschte Nachrichten.
- Der Postfachsuchordner des Benutzers befindet sich in einem Fehlerstatus.
- Exchange Online Organisationen, in denen Exclaimer aktiviert ist. Informationen zum Beheben dieses Problems finden Sie unter [KB4014438.](https://support.microsoft.com/help/4014438)
- [S/MIME)](/exchange/security-and-compliance/smime-exo/smime-exo) verschlüsselte Nachrichten.
- Sie haben die Aktion "Dynamische Zustellung" in einer Tresor Anlagenrichtlinie konfiguriert, aber der Empfänger unterstützt die dynamische Zustellung nicht (z. B. ist der Empfänger ein Postfach in einer lokalen Exchange Organisation). Tresor [Links in Microsoft Defender für Office 365](set-up-safe-links-policies.md) können jedoch Office Dateianlagen überprüfen, die URLs enthalten (je nachdem, wie die globalen Einstellungen für Tresor [Links](configure-global-settings-for-safe-links.md) konfiguriert sind).

## <a name="submitting-files-for-malware-analysis"></a>Übermitteln von Dateien für die Schadsoftwareanalyse

- Wenn Sie eine Datei erhalten, die Sie zur Analyse an Microsoft senden möchten, finden Sie weitere Informationen unter [Übermitteln von Schadsoftware und Nicht-Schadsoftware an Microsoft zur Analyse.](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)
- Wenn Sie eine E-Mail-Nachricht (mit oder ohne Anlage) erhalten, die Sie zur Analyse an Microsoft übermitteln möchten, lesen Sie ["Nachrichten und Dateien an Microsoft melden".](report-junk-email-messages-to-microsoft.md)
