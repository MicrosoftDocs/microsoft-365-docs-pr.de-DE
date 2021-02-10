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
description: Administratoren können sich über das Feature "Sichere Anlagen" in Microsoft Defender für Office 365 informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e85695a6d0fba221f3c614ec33b3552d37153e2
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175847"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Sichere Anlagen in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Sichere Anlagen in [Microsoft Defender für Office 365](office-365-atp.md) bieten eine zusätzliche Schutzebene für E-Mail-Anlagen, die bereits vom Schutz vor Schadsoftware [in Exchange Online Protection (EOP)](anti-malware-protection.md)überprüft wurden. Insbesondere verwenden sichere Anlagen eine virtuelle Umgebung, um Anlagen in E-Mail-Nachrichten zu überprüfen, bevor sie an Empfänger übermittelt werden (ein Prozess, der als _Detonation bekannt ist)._

Der Schutz sicherer Anlagen für E-Mail-Nachrichten wird durch Richtlinien für sichere Anlagen gesteuert. Es gibt keine Standardrichtlinie für sichere Anlagen. Um den Schutz sicherer Anlagen zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere **Anlagen erstellen.** Anweisungen finden Sie unter ["Einrichten von Richtlinien für sichere Anlagen in Defender für Office 365".](set-up-atp-safe-attachments-policies.md)

In der folgenden Tabelle werden Szenarien für sichere Anlagen in Microsoft 365- und Office 365-Organisationen beschrieben, die Microsoft Defender für Office 365 enthalten (mit anderen Worten: Fehlende Lizenzierung ist in den Beispielen nie ein Problem).

****

|Szenario|Ergebnis|
|---|---|
|Pats Microsoft 365 E5-Organisation hat keine Richtlinien für sichere Anlagen konfiguriert.|Pat ist nicht durch sichere Anlagen geschützt. <p> Ein Administrator muss mindestens eine Richtlinie für sichere Anlagen erstellen, damit der Schutz sicherer Anlagen aktiv ist. Darüber hinaus müssen die Bedingungen der Richtlinie Pat enthalten, wenn Pat durch sichere Anlagen geschützt werden soll.|
|Lees Organisation verfügt über eine Richtlinie für sichere Anlagen, die nur für Finanzmitarbeiter gilt. Lee ist Mitglied der Vertriebsabteilung.|Lee ist nicht durch sichere Anlagen geschützt. <p> Finanzmitarbeiter sind durch sichere Anlagen geschützt, Vertriebsmitarbeiter (und andere Mitarbeiter) dagegen nicht.|
|Ein Administrator in seiner Organisation hat gestrigen eine Richtlinie für sichere Anlagen erstellt, die für alle Mitarbeiter gilt. Heute hat er eine E-Mail-Nachricht empfangen, die eine Anlage enthält.|Dieser wird durch sichere Anlagen geschützt. <p> In der Regel dauert es ungefähr 30 Minuten, bis eine neue Richtlinie wirksam wird.|
|Chris' Organisation verfügt über lange Zeit richtlinien für sichere Anlagen für alle In der Organisation. Chris empfängt eine E-Mail mit einer Anlage und gibt die Nachricht dann an externe Empfänger weiter.|Chis sind durch sichere Anlagen geschützt. <p> Wenn die externen Empfänger auch über Richtlinien für sichere Anlagen in ihrer Organisation verfügen, unterliegen die weitergeleiteten Nachrichten diesen Richtlinien.|
|

Die Überprüfung auf sichere Anlagen findet in derselben Region statt, in der sich Ihre Microsoft 365-Daten befinden. Weitere Informationen zur Geografie des Rechenzentrums finden Sie unter ["Wo befinden sich Ihre Daten?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Die folgenden Features befinden sich in den globalen Einstellungen der Richtlinien für sichere Anlagen im Security & Compliance Center, aber diese Einstellungen sind global aktiviert oder deaktiviert und erfordern keine Richtlinien für sichere Anlagen:
>
> - [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams.](atp-for-spo-odb-and-teams.md)
>
> - [Sichere Dokumente in Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Richtlinieneinstellungen für sichere Anlagen

In diesem Abschnitt werden die Einstellungen in den Richtlinien für sichere Anlagen beschrieben:

- **Antwort auf unbekannte Schadsoftware** für sichere Anlagen: Diese Einstellung steuert die Aktion für die Schadsoftwareprüfung für sichere Anlagen in E-Mail-Nachrichten. Die verfügbaren Optionen werden in der folgenden Tabelle beschrieben:

  ****

  |Option|Effekt|Verwenden Sie diese, wenn Sie:|
  |---|---|---|
  |**Aus**|Anlagen werden von "Sichere Anlagen" nicht auf Schadsoftware überprüft. Nachrichten werden weiterhin durch den Ansoftwareschutz in EOP auf [Schadsoftware überprüft.](anti-malware-protection.md)|Deaktivieren Sie die Überprüfung für ausgewählte Empfänger. <p> Vermeiden Sie unnötige Verzögerungen beim Routing interner E-Mails. <p> **Diese Option wird für die meisten Benutzer nicht empfohlen. Sie sollten diese Option nur verwenden, um die Überprüfung auf sichere Anlagen für Empfänger zu deaktivieren, die nur Nachrichten von vertrauenswürdigen Absendern empfangen.**|
  |**Überwachen**|Übermittelt Nachrichten mit Anlagen und verfolgt dann, was mit erkannter Schadsoftware passiert. <p> Die Zustellung sicherer Nachrichten kann aufgrund der Überprüfung auf sichere Anlagen verzögert werden.|Sehen Sie, wo erkannte Schadsoftware in Ihrer Organisation enthalten ist.|
  |**Block**|Verhindert, dass Nachrichten mit erkannten Schadsoftwareanlagen zugestellt werden. <p> Nachrichten werden [unter Quarantäne](manage-quarantined-messages-and-files.md) gestellt, in denen nur Administratoren (nicht Endbenutzer) die Nachrichten überprüfen, veröffentlichen oder löschen können. <p> Blockiert automatisch zukünftige Instanzen der Nachrichten und Anlagen. <p> Die Zustellung sicherer Nachrichten kann aufgrund der Überprüfung auf sichere Anlagen verzögert werden.|Schützt Ihre Organisation vor wiederholten Angriffen mit denselben Schadsoftwareanlagen. <p> Dies ist der Standardwert und der empfohlene Wert in den voreingestellten Standard- und [Strict-Sicherheitsrichtlinien.](preset-security-policies.md)|
  |**Replace**|Entfernt erkannte Anlagen mit Schadsoftware. <p> Benachrichtigt Empfänger, dass Anlagen entfernt wurden. <p>  Nachrichten werden [unter Quarantäne](manage-quarantined-messages-and-files.md) gestellt, in denen nur Administratoren (nicht Endbenutzer) die Nachrichten überprüfen, veröffentlichen oder löschen können. <p> Die Zustellung sicherer Nachrichten kann aufgrund der Überprüfung auf sichere Anlagen verzögert werden.|Erhöhen Sie die Sichtbarkeit für Empfänger, dass Anlagen aufgrund erkannter Schadsoftware entfernt wurden.|
  |**Dynamische Übermittlung**|Übermittelt Nachrichten sofort, ersetzt anlagen jedoch durch Platzhalter, bis die Überprüfung auf sichere Anlagen abgeschlossen ist. <p> Weitere Informationen finden Sie im Abschnitt "Richtlinien für die dynamische Zustellung in sicheren [Anlagen"](#dynamic-delivery-in-safe-attachments-policies) weiter später in diesem Artikel.|Vermeiden Sie Nachrichtenverzögerungen, während Sie Empfänger vor schädlichen Dateien schützen. <p> Ermöglichen Sie Empfängern die Vorschau von Anlagen im abgesicherten Modus, während die Überprüfung stattfindet.|
  |

- Anlage bei Erkennung  umleiten: Aktivieren Sie die Umleitung, und senden Sie die Anlage an die folgende E-Mail-Adresse: Senden Sie für Aktionen zum Blockieren, Überwachen oder Ersetzen Nachrichten, die Anlagen mit Schadsoftware enthalten, zur Analyse und Untersuchung an die angegebene interne oder externe E-Mail-Adresse.   

  Die Empfehlung für Standard- und Strict-Richtlinieneinstellungen besteht in der Aktivierung der Umleitung. Weitere Informationen finden Sie unter Einstellungen [für sichere Anlagen.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)

- **Wenden** Sie die oben aufgeführte Auswahl an, wenn bei  der Schadsoftwareprüfung auf Anlagen ein Zeitfehler auftritt oder ein Fehler auftritt: Die von "Sichere Anlagen" angegebene Aktion wird auf Nachrichten angewendet, auch wenn die Überprüfung auf sichere Anlagen nicht abgeschlossen werden kann. Wählen Sie diese Option immer aus, wenn Sie **"Umleitung aktivieren" auswählen.** Andernfalls gehen Nachrichten möglicherweise verloren.

- **Empfängerfilter:** Sie müssen die Empfängerbedingungen und Ausnahmen angeben, die bestimmen, für wen die Richtlinie gilt. Sie können die folgenden Eigenschaften für Bedingungen und Ausnahmen verwenden:

  - **Der Empfänger ist**
  - **Die Empfängerdomäne ist**
  - **Der Empfänger ist Mitglied von**

  Sie können eine Bedingung oder Ausnahme nur einmal verwenden, die Bedingung oder Ausnahme kann aber mehrere Werte enthalten. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

- **Priorität:** Wenn Sie mehrere Richtlinien erstellen, können Sie die Reihenfolge angeben, in der sie angewendet werden. Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

  Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Dynamische Übermittlung in Richtlinien für sichere Anlagen

> [!NOTE]
> Die dynamische Zustellung funktioniert nur für Exchange Online-Postfächer.

Die Dynamische Zustellungsaktion in Richtlinien für sichere Anlagen versucht, Verzögerungen bei der E-Mail-Zustellung zu beseitigen, die möglicherweise durch die Überprüfung sicherer Anlagen verursacht werden. Der Text der E-Mail-Nachricht wird mit einem Platzhalter für jede Anlage an den Empfänger zugestellt. Der Platzhalter bleibt erhalten, bis die Anlage als sicher eingestuft wird und die Anlage dann zum Öffnen oder Herunterladen verfügbar wird.

Wenn festgestellt wird, dass eine Anlage schädlich ist, wird die Nachricht unter Quarantäne gestellt. Nur Administratoren (nicht Endbenutzer) können Nachrichten, die bei der Überprüfung sicherer Anlagen unter Quarantäne gestellt wurden, überprüfen, veröffentlichen oder löschen. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator.](manage-quarantined-messages-and-files.md)

Die meisten PDFs und Office-Dokumente können im abgesicherten Modus in der Vorschau angezeigt werden, während die Überprüfung auf sichere Anlagen ausgeführt wird. Wenn eine Anlage nicht mit der Vorschau für die dynamische Zustellung kompatibel ist, wird den Empfängern ein Platzhalter für die Anlage angezeigt, bis die Überprüfung auf sichere Anlagen abgeschlossen ist.

Wenn Sie ein mobiles Gerät verwenden und PDFs nicht im Vorschaufeld für die dynamische Übermittlung auf Ihrem mobilen Gerät gerendert werden, versuchen Sie, die Nachricht in Outlook im Web (früher als Outlook Web App bezeichnet) mit Ihrem mobilen Browser zu öffnen.

Hier sind einige Überlegungen für die dynamische Zustellung und weitergeleitete Nachrichten:

- Wenn der weitergeleitete Empfänger durch eine Richtlinie für sichere Anlagen geschützt ist, die die Option "Dynamische Zustellung" verwendet, wird dem Empfänger der Platzhalter mit der Möglichkeit angezeigt, eine Vorschau kompatibler Dateien anzuzeigen.

- Wenn der weitergeleitete Empfänger nicht durch eine Richtlinie für sichere Anlagen geschützt ist, werden die Nachricht und anlagen ohne Überprüfung auf sichere Anlagen oder Anlagenplatzhalter zugestellt.

Es gibt Szenarien, in denen die dynamische Zustellung Anlagen in Nachrichten nicht ersetzen kann. Diese Szenarien umfassen:

- Nachrichten in öffentlichen Ordnern.

- Nachrichten, die mithilfe von benutzerdefinierten Regeln aus dem Postfach und dann zurück in das Postfach eines Benutzers geroutet werden.

- Nachrichten, die (automatisch oder manuell) aus Cloudpostfächern an andere Speicherorte verschoben werden, einschließlich Archivordnern.

- Gelöschte Nachrichten.

- Der Postfachsuchordner des Benutzers befindet sich in einem Fehlerstatus.

- Exchange Online-Organisationen, in denen Exclaimer aktiviert ist. Informationen zum Beheben dieses Problems finden Sie unter [KB4014438](https://support.microsoft.com/help/4014438).

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) verschlüsselte Nachrichten.

- Sie haben die Dynamische Zustellungsaktion in einer Richtlinie für sichere Anlagen konfiguriert, aber der Empfänger unterstützt die dynamische Zustellung nicht (z. B. ist der Empfänger ein Postfach in einer lokalen Exchange-Organisation). Sichere Links [in Microsoft Defender für Office 365](set-up-atp-safe-links-policies.md) können jedoch In-Office-Dateianlagen überprüfen, die URLs enthalten (je nachdem, wie die globalen Einstellungen für sichere Links [konfiguriert](configure-global-settings-for-safe-links.md) sind).

## <a name="submitting-files-for-malware-analysis"></a>Übermitteln von Dateien für die Schadsoftwareanalyse

- Wenn Sie eine Datei erhalten, die Sie zur Analyse an Microsoft senden möchten, lesen Sie "Schadsoftware und Nicht-Schadsoftware zur Analyse an [Microsoft übermitteln".](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)

- Wenn Sie eine E-Mail-Nachricht (mit oder ohne Anlage) erhalten, die Sie zur Analyse an Microsoft übermitteln möchten, lesen Sie "Nachrichten und Dateien an [Microsoft melden".](report-junk-email-messages-to-microsoft.md)
