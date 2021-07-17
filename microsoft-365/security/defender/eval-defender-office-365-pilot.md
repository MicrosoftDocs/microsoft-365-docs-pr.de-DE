---
title: Pilotieren von Microsoft Defender für Office 365, Verwenden der Evaluierung in Ihrer Produktionsumgebung, Fördern der Evaluierung in der Produktion, Erfahren Sie, wie Sie Defender bewerten.
description: Schritte zum Testen der Evaluierung mit Gruppen aktiver und vorhandener Benutzer, um die Features von Microsoft Defender für Office 365 ordnungsgemäß zu testen.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/25/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 86f8dcc7b5e06605042f609ede4027510663cc65
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458241"
---
# <a name="pilot-microsoft-defender-for-office-365"></a>Pilotprojekt für Microsoft Defender für Office 365
**Gilt für:**
- Microsoft 365 Defender

Dieser Artikel ist [Schritt 3 von 3](eval-defender-office-365-overview.md) beim Einrichten der Evaluierungsumgebung für Microsoft Defender für Office 365. Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-office-365-overview.md)

Führen Sie die folgenden Schritte aus, um das Pilotprojekt für Microsoft Defender für Office 365 einzurichten und zu konfigurieren.

![Schritte zum Erstellen des Pilotprojekts für Microsoft Defender für Office 365](../../media/defender/m365-defender-office-pilot.png)

- [Schritt 1: Erstellen von Pilotgruppen](#step-1-create-pilot-groups)
- [Schritt 2: Konfigurieren des Schutzes](#step-2-configure-protection)
- [Schritt 3: Testen von Funktionen – Machen Sie sich mit Simulation, Überwachung und Metriken vertraut](#step-3-try-out-capabilities--get-familiar-with-simulation-monitoring-and-metrics)

Wenn Sie Microsoft Defender für Office 365 auswerten, können Sie bestimmte Benutzer testen, bevor Sie Richtlinien für Ihre gesamte Organisation aktivieren und erzwingen. Durch das Erstellen von Verteilergruppen können Sie die Bereitstellungsprozesse verwalten. Erstellen Sie beispielsweise Gruppen wie *Defender für Office 365 Benutzer – Standardschutz*, Defender für Office 365 Benutzer – *Strenger Schutz*, Defender für Office 365 Benutzer – *Benutzerdefinierter Schutz* oder Defender für Office 365 Benutzer – *Ausnahmen.*

Es ist möglicherweise nicht offensichtlich, warum "Standard" und "Streng" die dafür verwendeten Begriffe sind. Dies wird jedoch deutlich, wenn Sie mehr über Defender für Office 365 Sicherheitsvoreinstellungen erfahren. Benennungsgruppen "benutzerdefinierte" und "Ausnahmen" sprechen für sich selbst, und obwohl die meisten Ihrer Benutzer unter *standard-* und *strenge* Fallen fallen sollten, sammeln benutzerdefinierte und Ausnahmegruppen wertvolle Daten zum Verwalten von Risiken für Sie.

## <a name="step-1-create-pilot-groups"></a>Schritt 1: Erstellen von Pilotgruppen

Verteilergruppen können direkt in Exchange Online erstellt und definiert oder aus dem lokalen Active Directory synchronisiert werden.

1. Melden Sie sich bei Exchange Admin Center (EAC) mit einem Konto an, dem die Rolle "Empfängeradministrator" zugewiesen wurde oder gruppenverwaltungsberechtigungen delegiert wurden.
2. Erweitern Sie im Navigationsmenü *"Empfänger",* und wählen Sie *"Gruppen"* aus.

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text="Exchange Admin Center im Navigationsmenü (Schnellstart) mit einem Pfeil, der auf Gruppen zeigt. Klicken Sie auf &quot;Gruppen&quot;.":::

3. Wählen Sie im Dashboard "Gruppen" die Option "Gruppe hinzufügen" aus.

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="Fügen Sie Im Bereich &quot;Gruppen&quot; Gruppen hinzu.":::

4. Wählen Sie für den Gruppentyp *"Verteilung"* aus, und klicken Sie auf "Weiter".

:::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text="Wählen Sie hier einen Verteilergruppentyp aus.":::

5. Geben Sie der Gruppe einen Namen und eine Beschreibung, und klicken Sie dann auf "Weiter".

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="Benennen und beschreiben Sie die Gruppe.":::

## <a name="step-2-configure-protection"></a>Schritt 2: Konfigurieren des Schutzes

Einige Funktionen in Defender für Office 365 sind standardmäßig konfiguriert und aktiviert, aber bei Sicherheitsvorgängen kann es sinnvoll sein, den Schutz vor dem Standard zu erhöhen.

Einige Funktionen sind *noch nicht* konfiguriert. Sie haben drei Optionen zum Konfigurieren des Schutzes:

- **Automatisches Zuweisen voreingestellter Sicherheitsrichtlinien** – [Voreingestellte Sicherheitsrichtlinien](../office-365-security/preset-security-policies.md) werden als Methode bereitgestellt, um schnell ein einheitliches Schutzniveau für alle Funktionen zuzuweisen. Sie können aus **_standard_*_ oder _*_strict_** auswählen. Ein guter Ansatz besteht darin, mit vordefinierten Sicherheitsrichtlinien zu beginnen und dann die Richtlinien zu optimieren, während Sie mehr über die Funktionen und Ihre eigene einzigartige Bedrohungsumgebung erfahren. Der Vorteil hier besteht darin, dass Sie Benutzergruppen so schnell wie möglich schützen und anschließend den Schutz optimieren können. (Diese Methode wird empfohlen.)
- **Manuelles Konfigurieren des grundlegenden Schutzes** – Wenn Sie es vorziehen, die Umgebung selbst zu konfigurieren, können Sie schnell eine *Baseline* des Schutzes erreichen, indem Sie die Anleitung unter ["Schutz vor Bedrohungen"](../office-365-security/protect-against-threats.md)befolgen. Bei diesem Ansatz erfahren Sie mehr über die konfigurierbaren Einstellungen. Und natürlich können Sie die Richtlinien später optimieren.
- **Konfigurieren von *benutzerdefinierten* Schutzrichtlinien** – Sie können auch benutzerdefinierte Schutzrichtlinien als Teil Ihrer Evaluierung erstellen und zuweisen. Bevor Sie mit dem Anpassen von Richtlinien beginnen, ist es wichtig, die Rangfolge zu verstehen, in der diese Schutzrichtlinien angewendet und erzwungen werden. Sicherheitsfunktionen müssen einige Richtlinien erstellen, auch wenn die Voreinstellung angewendet wird, um Sicherheitsrichtlinien für Tresor Links und Tresor Anlagen zu definieren.

> [!IMPORTANT]
> **Wenn Sie benutzerdefinierte Schutzrichtlinien konfigurieren müssen,** sollten Sie die Werte untersuchen, aus denen die **Standard-** und Strict-Sicherheitsdefinitionen bestehen: *[Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365 Sicherheit.](../office-365-security/recommended-settings-for-eop-and-office365.md)*  Standardwerte, die vor der Konfiguration angezeigt werden, werden ebenfalls aufgeführt. Behalten Sie eine Kalkulationstabelle vor, in der Ihr benutzerdefinierter Build abweicht.

### <a name="assign-preset-security-policies"></a>Zuweisen voreingestellter Sicherheitsrichtlinien

Es wird empfohlen, bei der Bewertung von MDO mit den *empfohlenen Basisrichtlinien* zu beginnen und sie dann im Verlauf des Evaluierungszeitraums nach Bedarf zu verfeinern.

Sie können empfohlene EOP und Defender für Office 365-Schutzrichtlinien schnell aktivieren und sie bestimmten Pilotbenutzern oder definierten Gruppen als Teil Ihrer Bewertung zuweisen. Voreingestellte Richtlinien bieten eine standardbasierte **Standardschutzvorlage** oder eine aggressivere Strict-Schutzvorlage, die unabhängig voneinander zugewiesen oder kombiniert werden kann. 

Nachfolgend finden Sie die [vordefinierten Sicherheitsrichtlinien in EOP und Microsoft Defender für Office 365](../office-365-security/preset-security-policies.md) Artikel, in dem die Schritte beschrieben werden.

1. Melden Sie sich bei Ihrem Microsoft 365 Mandanten an. Verwenden Sie ein Konto mit Zugriff auf das Microsoft 365 Defender-Portal, das der Organisationsverwaltungsrolle in Office 365 hinzugefügt wurde, oder die Rolle "Sicherheitsadministrator" in Microsoft 365.
2. Wählen Sie im *Navigationsmenü "Richtlinien & Regeln"* unter "E-Mail & Zusammenarbeit" aus.

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-pilot-policies.png" alt-text="Klicken Sie im Navigationsbereich unter &quot;E-Mail & Zusammenarbeit&quot; auf &quot;Richtlinien & Regeln&quot;.":::

3. Klicken Sie im Dashboard "Richtlinie & Regeln" auf *"Bedrohungsrichtlinien".*

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png" alt-text="a":::

4. Erweitern Sie im Microsoft 365 Defender Portal die Bedrohungsverwaltung im Navigationsmenü, und wählen Sie dann im Untermenü "Richtlinie" aus.
5. Klicken Sie im Richtliniendashboard auf *"Voreingestellte Sicherheitsrichtlinien".*

:::image type="content" source="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png" alt-text="Klicken Sie auf die Kachel &quot;Voreingestellte Sicherheitsrichtlinien&quot;.":::

6. Klicken Sie auf *"Bearbeiten",* um die Standardrichtlinie und/oder die Strict-Richtlinie zu konfigurieren und zuzuweisen. :::image type="content" source="../../media/mdo-eval/8-mdo-eval-pilot-preset.png" alt-text="Klicken Sie im Bereich &quot;Voreingestellte Sicherheitsrichtlinien&quot; auf &quot;Bearbeiten&quot;.":::
7. Fügen Sie Bedingungen hinzu, um baseline ***EOP** _ Schutzmechanismen bei Bedarf auf bestimmte Pilotbenutzer oder Benutzergruppen anzuwenden, und wählen Sie _Next* aus, um fortzufahren.
    - Beispielsweise kann eine Defender für Office 365 Bedingung für Pilotauswertungen angewendet werden, wenn die Empfänger *Mitglieder* einer definierten *Defender for Office 365 Standard Protection-Gruppe* sind und dann verwaltet werden, indem einfach Konten zu der Gruppe hinzugefügt oder das Konto entfernt wird.
 :::image type="content" source="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png" alt-text="Fügen Sie die erforderlichen Bedingungen hinzu, um die EOP-Sicherheitsstufe auf Ihre Pilotgruppe anzuwenden.":::

8. Fügen Sie Bedingungen hinzu, um basisplanbezogene ***MDO** _-Schutzmaßnahmen bei Bedarf auf bestimmte Pilotbenutzer oder Benutzergruppen anzuwenden. Klicken Sie auf _Next*, um fortzufahren.
    - Beispielsweise könnte eine Defender für Office 365 Bedingung für Pilotauswertungen angewendet werden, wenn die Empfänger *Mitglieder* einer definierten *Defender für Office 365 Standard Protection-Gruppe* sind und dann verwaltet werden, indem einfach Konten über die Gruppe hinzugefügt/entfernt werden.
  :::image type="content" source="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png" alt-text="Fügen Sie die erforderlichen Bedingungen hinzu, um den Defender für Office 365 Sicherheitsstufe auf Ihre Pilotgruppe anzuwenden.":::

9. Überprüfen und bestätigen Sie Ihre Änderungen für die Zuweisung voreingestellter Sicherheitsrichtlinien.
10. Voreingestellte Schutzrichtlinien können verwaltet werden (neu konfiguriert, erneut angewendet, deaktiviert usw.), indem Sie zum Microsoft 365 Defender Portal > Richtlinien & Regeln > Bedrohungsrichtlinien > zurückkehren und auf die Kachel *"Voreingestellte Sicherheitsrichtlinien"* klicken.

### <a name="configure-custom-protection-policies"></a>Konfigurieren von benutzerdefinierten Schutzrichtlinien

Die vordefinierten *Standard-* oder *Strict* Defender für Office 365 Richtlinienvorlagen bieten Den Pilotbenutzern den empfohlenen Grundlegenden Schutz. Sie können jedoch auch benutzerdefinierte Schutzrichtlinien als Teil Ihrer Auswertung erstellen und zuweisen.

Es ist *wichtig* zu wissen, welche Priorität diese Schutzrichtlinien bei Anwendung und Durchsetzung haben, wie [Reihenfolge und Rangfolge des E-Mail-Schutzes – Office 365](../office-365-security/how-policies-and-protections-are-combined.md) erläutert.

Die folgende Tabelle enthält Verweise und zusätzliche Anleitungen zum Konfigurieren und Zuweisen von benutzerdefinierten Schutzrichtlinien:

|Richtlinie   |Beschreibung  |Referenz  |
|:---------:|---------|---------|
|Verbindungsfilterung     |    Identifizieren Sie gute oder schlechte Quell-E-Mail-Server anhand ihrer IP-Adressen.     |     [Konfigurieren der Standardverbindungsfilterrichtlinie in EOP](../office-365-security/configure-the-connection-filter-policy.md)    |
|Antischadsoftware    |    Schützen Sie Benutzer vor E-Mail-Schadsoftware, einschließlich der zu ergreifenden Maßnahmen und der Personen, die benachrichtigt werden sollen, wenn Schadsoftware erkannt wird.     |    [Konfigurieren von Antischadsoftwarerichtlinien in EOP](../office-365-security/configure-anti-malware-policies.md)     |
|Antispoofing     |  Schützen Sie Benutzer vor Spoofingversuchen, indem Sie Spoofintelligenz und Spoofintelligenz-Einblicke verwenden.   |     [Konfigurieren der Spoofintelligenz in Defender für Office 365](../office-365-security/learn-about-spoof-intelligence.md)    |
|Antispam     |    Schützen Sie Benutzer vor E-Mail-Spam, einschließlich der Aktionen, die ausgeführt werden müssen, wenn Spam erkannt wird.     |    [Konfigurieren von Antispamrichtlinien in Defender für Office 365](../office-365-security/configure-your-spam-filter-policies.md)     |
|Antiphishing     |   Schützen von Benutzern vor Phishingangriffen und Konfigurieren von Sicherheitstipps für verdächtige Nachrichten      |     [Konfigurieren von Antiphishing-Richtlinien in Microsoft Defender für Office 365](../office-365-security/configure-mdo-anti-phishing-policies.md)    |
|Sichere Anlagen     |    Schützen Sie Benutzer vor schädlichen Inhalten in E-Mail-Anlagen und Dateien in SharePoint, OneDrive und Teams.     |    [Einrichten von Richtlinien für sichere Anlagen in Defender für Office 365](../office-365-security/set-up-safe-attachments-policies.md)     |
|Sichere Links     |     Schützen Sie Benutzer davor, schädliche Links in E-Mail-Nachrichten oder Office Desktop-Apps zu öffnen und freizugeben.    |    [Einrichten von Richtlinien für sichere Links in Defender für Office 365](../office-365-security/set-up-safe-links-policies.md)     |

## <a name="step-3-try-out-capabilities--get-familiar-with-simulation-monitoring-and-metrics"></a>Schritt 3: Testen von Funktionen – Machen Sie sich mit Simulation, Überwachung und Metriken vertraut

Nachdem Ihr Pilotprojekt eingerichtet und konfiguriert wurde, ist es hilfreich, sich mit den Berichterstattungs-, Überwachungs- und Angriffssimulationstools vertraut zu machen, die für Microsoft Defender für Microsoft 365 einzigartig sind.

|Funktion  |Beschreibung  |Weitere Informationen  |
|---------|---------|---------|
|Sicherheitsrisiken-Explorer     | Der Bedrohungs-Explorer ist ein leistungsstarkes Nahezu-Echtzeit-Tool, das Sicherheitsteams dabei unterstützt, Bedrohungen zu untersuchen und darauf zu reagieren und Informationen zu verdächtiger Schadsoftware und Phishing in E-Mails und Dateien in Office 365 sowie andere Sicherheitsbedrohungen und Risiken für Ihre Organisation anzuzeigen.        | [Ansichten im Bedrohungs-Explorer und Echtzeiterkennungen ](../office-365-security/threat-explorer-views.md)       | 
|Angriffssimulator     | Sie können die Angriffssimulationsschulung im Microsoft Defender 365-Portal verwenden, um realistische Angriffsszenarien in Ihrer Organisation auszuführen, die Ihnen helfen, anfällige Benutzer zu identifizieren und zu finden, bevor sich ein realer Angriff auf Ihre Umgebung auswirkt.        |  [Angriffssimulator in Microsoft Defender für Office 365](../office-365-security/attack-simulator.md)       |
|Dashboard "Berichte"     | Klicken Sie im linken Navigationsmenü auf "Berichte", und erweitern Sie die Überschrift "E-Mail & Zusammenarbeit". In den E-Mail-& Berichten zur Zusammenarbeit geht es um die Ermittlung von Sicherheitstrends, von denen einige Ihnen die Möglichkeit geben, Maßnahmen zu ergreifen (über Schaltflächen wie "Gehe zu Übermittlungen"), und andere, die Trends anzeigen, z. B. Nachrichtenflussstatuszusammenfassung, häufigste Schadsoftware, Spooferkennungen, kompromittierte Benutzer, E-Mail-Latenz, Tresor Links und Tresor Anlagenberichte. Diese Metriken werden automatisch generiert.  |    [Anzeigen von Berichten](../office-365-security/view-email-security-reports.md)     |

## <a name="next-steps"></a>Nächste Schritte


[Auswerten des Microsoft Defender für Endpunkt](eval-defender-endpoint-overview.md)

Kehren Sie zur Übersicht für ["Auswerten von Microsoft Defender für Office 365"](eval-defender-office-365-overview.md) zurück.

Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)