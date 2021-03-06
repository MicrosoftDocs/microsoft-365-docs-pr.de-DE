---
title: Schützen von Informationen, die der Datenschutzbestimmungen unterliegen
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Stellen Sie Microsoft 365 Sicherheits- und Compliancefeatures bereit und schützen Sie Ihre persönlichen Informationen.
ms.openlocfilehash: 7325aad0392d559703199c81f2544a582d7eadcb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287747"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Schützen von Informationen, die der Datenschutzbestimmungen unterliegen

In Ihrem Abonnement können eine Reihe von Informationsschutz-Steuerelementen eingesetzt werden, um die Anforderungen und Vorschriften zur Einhaltung des Datenschutzes zu erfüllen. Dazu gehören die Datenschutz-Grundverordnung (DSGVO), HIPAA-HITECH (Us Health Care Privacy Act), das California Consumer Protection Act (CCPA) und das Brazil Data Protection Act (LGPD).

Diese Steuerelemente befinden sich in den folgenden Lösungsbereichen:

- Vertraulichkeitsbezeichnungen
- Verhinderung von Datenverlusten (Data Loss Prevention, DLP)
- Office-Nachrichtenverschlüsselung (Office Message Encryption, OME)
- zugriffssteuerungen für Teams und Websites

![Wichtige Dienste zum Schutz personenbezogener Informationen, die der Datenschutzbestimmungen unterliegen](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

> [!NOTE]
> Diese Lösung beschreibt Sicherheits- und Compliancefeatures zum Schutz von Informationen, die den Datenschutzbestimmungen unterliegen. Eine vollständige Liste der Sicherheitsfeatures in Microsoft 365 finden Sie in [Microsoft 365 Sicherheitsdokumentation.](../security/index.yml) Eine vollständige Liste der Compliancefeatures in Microsoft 365 finden Sie in [Microsoft 365 Compliancedokumentation.](../compliance/index.yml)

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Datenschutzbestimmungen, die sich auf Steuerelemente zum Informationsschutz auswirken

Nachfolgend finden Sie eine Beispielliste der Datenschutzbestimmungen, die sich auf Steuerelemente zum Informationsschutz beziehen können:

- DSGVO Artikel 5 (1) (f))
- DSGVO-Artikel (32)(1) (a)
- LGPD Artikel 46
- HIPAA-HITECH (45 CFR 164.312(e)(1))
- HIPAA-HITECH (45 C.F.R. 164.312(e)(2)(ii))

Weitere Informationen zu den oben genannten Informationen finden Sie im Artikel "Bewerten von [Datenschutzrisiken und Identifizieren vertraulicher Elemente".](information-protection-deploy-assess.md)

Datenschutzbestimmungen für den Informationsschutz empfehlen:

- Schutz vor Verlust oder unbefugtem Zugriff, Nutzung und/oder Übertragung.
- Risikobasierte Anwendung von Schutzmechanismen.
- Verwendung der Verschlüsselung, sofern zutreffend.

Ihre Organisation möchte möglicherweise auch Microsoft 365 Inhalte für andere Zwecke, z. B. andere Complianceanforderungen oder aus geschäftlichen Gründen, schützen. Die Einrichtung Ihres Informationsschutzschemas für den Datenschutz sollte im Rahmen der allgemeinen Planung, Implementierung und Verwaltung des Informationsschutzes erfolgen.

Um Ihnen die ersten Schritte mit einem Informationsschutzschema in Microsoft 365 zu erleichtern, enthält der folgende Abschnitt eine kurze Liste der zugehörigen Funktionen und Verbesserungsmaßnahmen für Microsoft 365. Die Liste enthält Funktionen und Verbesserungsmaßnahmen, die für Datenschutzbestimmungen gelten. Die Liste enthält jedoch keine älteren Technologien, wenn es eine neuere Funktion gibt, die die ältere größtenteils ersetzt. Beispielsweise ist information Rights Management (IRM) für SharePoint und OneDrive nicht in der Liste enthalten, aber Vertraulichkeitsbezeichnungen sind enthalten.

## <a name="managing-information-protection-in-microsoft-365"></a>Verwalten des Informationsschutzes in Microsoft 365

Microsoft [Information Protection-Lösungen](../compliance/information-protection.md) umfassen eine Reihe integrierter Funktionen in Microsoft 365, Microsoft Azure und Microsoft Windows. In Microsoft 365 umfassen Informationsschutzlösungen Folgendes:

- [Typen vertraulicher Informationen](../compliance/sensitive-information-type-entity-definitions.md) (im Artikel "Bewerten von [Datenschutzrisiken und Identifizieren vertraulicher Elemente")](information-protection-deploy-assess.md)
- [Vertraulichkeitsbezeichnungen](../compliance/sensitivity-labels.md)
  - Dienst-/Containerebene
  - Clientseitige/Inhaltsebene
  - Automatisiert für Ruhedaten in SharePoint und OneDrive
- Verhinderung von Datenverlust (Data Loss Prevention, DLP)
- [Microsoft 365 Verhinderung von Datenverlust am Endpunkt](../compliance/endpoint-dlp-learn-about.md)
- [Office 365-Nachrichtenverschlüsselung neue Funktionen (OME)](../compliance/ome.md) und OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md)

Darüber hinaus sind der Schutz auf Website- und Bibliotheksebene wichtige Mechanismen, die in jedes Schutzschema eingeschlossen werden müssen.

Informationen zu anderen Informationsschutzfunktionen außerhalb von Microsoft 365 finden Sie unter:

- [Microsoft Cloud Application Security (MCAS)](/cloud-app-security/)
- [Azure Information Protection](/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows Information Protection](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Mit Vertraulichkeitsbezeichnungen aus dem Microsoft Information Protection Framework können Sie die Daten Ihrer Organisation klassifizieren und schützen, ohne die Produktivität der Benutzer und deren Fähigkeit zur Zusammenarbeit zu beeinträchtigen.

> [!div class="mx-imgBorder"]
> ![Vertraulichkeitsbezeichnungen in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Voraussetzungen für Vertraulichkeitsbezeichnungen

Führen Sie diese Aktivitäten aus, bevor Sie eine der unten hervorgehobenen auf Vertraulichkeitsbezeichnungen basierenden Funktionen implementieren:

1. Verstehen Sie Folgendes:
   - **Geschäftliche Anforderungen.** Ermitteln Sie die geschäftlichen Gründe für die Anwendung von Vertraulichkeitsbezeichnungen in Ihrem Unternehmen. Beispielsweise Ihre Datenschutzanforderungen für den Informationsschutz.
   - **Vertraulichkeitsbezeichnungsfunktionen.** Vertraulichkeitsbezeichnungen können komplex werden. Lesen Sie daher unbedingt die Dokumentation zu [Vertraulichkeitsbezeichnungen,](../compliance/sensitivity-labels.md) bevor Sie beginnen.
   - **Wichtige Dinge, die Sie sich merken sollten** Vertraulichkeitsbezeichnungen werden im Microsoft Compliance Admin Center verwaltet, aber die Ziel- und Anwendungsoptionen variieren erheblich.
      - Es gibt Vertraulichkeitsbezeichnungen für Websites, Gruppen und Teams auf Containerebene (die Einstellungen gelten nicht für Inhalte innerhalb des Containers). Diese werden für Benutzer und Gruppen veröffentlicht, die sie anwenden, wenn eine Website, eine Gruppe oder ein Team bereitgestellt wird.
      - Es gibt Vertraulichkeitsbezeichnungen für aktive Inhalte. Diese werden auch für Benutzer oder Gruppen veröffentlicht, die sie entweder manuell anwenden oder automatisch angewendet werden, wenn:
        - Die Datei wird geöffnet/bearbeitet/gespeichert, entweder auf dem Desktop des Benutzers oder auf einer SharePoint Website.
        - Eine E-Mail ist unerzwendt und wird gesendet.
      - Es gibt Vertraulichkeitsbezeichnungen für die automatische Anwendung auf ruhenden Dateien in SharePoint und OneDrive zusätzlich zu E-Mails während der Übertragung über Exchange. Diese sind auf alle Websites oder bestimmte Websites ausgerichtet und gelten automatisch für die ruhenden Dateien in diesen Umgebungen.

2. Rationalisieren der aktuellen Vertraulichkeitsbezeichnungen mit früheren oder alternativen Methoden

   - Azure Information Protection

      Das aktuelle Vertraulichkeitsbezeichnungsschema muss möglicherweise mit jeder vorhandenen [Azure Information Protection-Implementierung](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection) für Bezeichnungen abgeglichen werden.
   - OME

      Wenn Sie planen, moderne Vertraulichkeitsbezeichnungen für den E-Mail-Schutz zu verwenden, und vorhandene E-Mail-Verschlüsselungsmethoden wie OME vorhanden sind, können sie koexistieren, aber Sie sollten die Szenarien kennen, in denen beide angewendet werden sollten. Weitere Informationen finden Sie [unter Office 365-Nachrichtenverschlüsselung neuen Funktionen (OME),](#office-365-message-encryption-ome-new-capabilities)die eine Tabelle enthält, in der der Schutz moderner Vertraulichkeitsbezeichnungen mit dem OME-basierten Schutz verglichen wird.

3. Planen der Integration in ein umfassenderes Informationsschutzschema. Zusätzlich zur Koexistenz mit OME können Vertraulichkeitsbezeichnungen neben Funktionen wie Microsoft 365 Verhinderung von Datenverlust (Data Loss Prevention, DLP) und Microsoft Cloud App Security verwendet werden. Informationen zum Erreichen ihrer Datenschutzziele finden Sie [in Microsoft Information Protection in Microsoft 365.](../compliance/information-protection.md)

4. Entwickeln Sie ein Klassifizierungs- und Kontrollschema für Vertraulichkeitsbezeichnungen. Siehe [Datenklassifizierung und Taxonomie von Vertraulichkeitsbezeichnungen.](https://aka.ms/dataclassificationwhitepaper)

### <a name="general-guidance"></a>Allgemeine Hinweise

1. **Schemadefinition.** Bevor Sie technische Funktionen zum Anwenden von Bezeichnungen und Schutz verwenden, arbeiten Sie organisationsweit an der Definition eines Klassifizierungsschemas. Möglicherweise verfügen Sie bereits über ein Klassifizierungsschema, das das Hinzufügen von personenbezogenen Daten erleichtert.
2. **Erste Schritte.** Entscheiden Sie zunächst über die Anzahl und die Namen von Bezeichnungen, die implementiert werden sollen. Führen Sie diese Aktivität aus, ohne sich Gedanken darüber zu machen, welche Technologie verwendet werden soll und wie Bezeichnungen angewendet werden. Wenden Sie dieses Schema universell in Ihrer gesamten Organisation an, einschließlich Daten, die sich lokal und in anderen Clouddiensten befinden.
3. **Weitere Empfehlungen** Berücksichtigen Sie beim Entwerfen und Implementieren von Richtlinien, Bezeichnungen und Bedingungen die folgenden Empfehlungen:

   - **Verwenden Sie vorhandenes Klassifizierungsschema (sofern vorhanden).** Viele Organisationen verwenden die Datenklassifizierung bereits in irgendeiner Form. Bewerten Sie das vorhandene Bezeichnungsschema sorgfältig, und verwenden Sie es nach Möglichkeit wie besehen. Die Verwendung vertrauter Bezeichnungen, die für Ihre Endbenutzer erkennbar sind, wird die Akzeptanz fördern.
   - **Beginnen Sie klein.** Es gibt praktisch keine Beschränkung für die Anzahl der Bezeichnungen, die Sie erstellen können. Eine große Anzahl von Bezeichnungen und Unterbezeichnungen kann jedoch die Akzeptanz verlangsamen.
   - **Verwenden Sie Szenarien und Anwendungsfälle.** Identifizieren Sie häufige Anwendungsfälle in Ihrer Organisation und verwenden Sie Szenarien, die von den Datenschutzbestimmungen abgeleitet sind, denen Sie unterliegen. Überprüfen Sie, ob die geplante Bezeichnungs- und Klassifizierungskonfiguration in der Praxis funktioniert.
   - **Stellen Sie jede Anforderung für eine neue Bezeichnung in Frage.** Benötigt jedes Szenario oder jeder Anwendungsfall wirklich eine neue Bezeichnung oder können Sie das verwenden, was Sie bereits haben? Wenn Sie die Anzahl der Bezeichnungen auf ein Minimum beschränken, wird die Akzeptanz verbessert.
   - **Verwenden Sie Unterbezeichnungen für wichtige Abteilungen.** Einige Abteilungen haben bestimmte Anforderungen, die bestimmte Bezeichnungen erfordern. Definieren Sie diese Bezeichnungen als Unterbezeichnungen für eine vorhandene Bezeichnung, und erwägen Sie die Verwendung bereichsspezifischer Richtlinien, die Benutzergruppen anstelle von global zugewiesen werden.
   - **Berücksichtigen Sie bereichsbezogene Richtlinien.** Richtlinien, die auf Untergruppen von Benutzern abzielen, verhindern eine Überladung von Bezeichnungen. Eine bereichsbezogene Richtlinie ermöglicht es, rollen- oder abteilungsspezifische Bezeichnungen oder Unterbezeichnungen nur Mitarbeitern zuzuweisen, die für diese bestimmte Abteilung arbeiten.
   - **Verwenden Sie aussagekräftige Bezeichnungsnamen.** Versuchen Sie nicht, Jargon, Standards oder Akronyme als Bezeichnungsnamen zu verwenden. Versuchen Sie, Namen zu verwenden, die mit dem Endbenutzer in Verbindung bringen, um die Akzeptanz zu verbessern. Anstatt Bezeichnungen wie PII, PCI, HIPAA, LBI, MBI und HBI zu verwenden, sollten Sie Namen wie "Non-Business", "Public", "General", "Confidential" und "Highly Confidential" in Betracht ziehen.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Erstellen und Bereitstellen von Vertraulichkeitsbezeichnungen für Websites, Gruppen und Teams

Wenn Sie [Vertraulichkeitsbezeichnungen](../compliance/sensitivity-labels-teams-groups-sites.md) im Microsoft 365 Compliance Center erstellen, können Sie sie jetzt auf diese Container anwenden:

- Microsoft Teams Websites
- Microsoft 365-Gruppen (früher Office 365-Gruppen)
- SharePoint-Websites

Verwenden Sie die folgenden Bezeichnungseinstellungen zum Schutz von Inhalt in diesen Containern:

- Datenschutz (öffentlich oder privat) von Microsoft 365 mit einer Gruppe verbundenen Teams Websites
- Zugriff externer Benutzer
- Zugriff von nicht verwalteten Geräten aus

Um die externe Freigabe für Container zu verhindern, die zum Speichern von Inhalten mit vertraulichen personenbezogenen Daten verwendet werden, markieren Sie die Dateien, die die Daten enthalten, als privat und erfordern verwaltete Geräte.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Erstellen und Bereitstellen von Vertraulichkeitsbezeichnungen für Inhalte

Vertraulichkeitsbezeichnungen, die auf Dateien angewendet werden, ermöglichen es Ihnen, ihre Inhalte zu verschlüsseln, den Inhalt zu kennzeichnen und andere Steuerelemente für Office Anwendungsinhalte zu definieren, einschließlich Outlook und Office im Web.

Wenn Sie bereit sind, die Daten Ihrer Organisation mit Vertraulichkeitsbezeichnungen zu schützen:

1. **Erstellen Sie die Bezeichnungen.** Erstellen und benennen Sie Ihre Vertraulichkeitsbezeichnungen gemäß der Klassifizierungstaxonomie Ihrer Organisation für unterschiedliche Vertraulichkeitsstufen von Inhalten. Weitere Informationen zum Entwickeln einer Klassifizierungstaxonomie finden Sie im [Whitepaper "Datenklassifizierung und Taxonomie von Vertraulichkeitsbezeichnungen".](https://aka.ms/dataclassificationwhitepaper)
2. **Legen Sie fest, wozu jede einzelne Bezeichnung dient.** Konfigurieren Sie die Schutzeinstellungen, die mit den einzelnen Bezeichnungen verknüpft werden sollen. Beispielsweise möchten Sie möglicherweise, dass für Inhalte mit niedriger Vertraulichkeit (z. B. eine Bezeichnung "Allgemein") nur eine Kopf- oder Fußzeile angewendet wird, während für Inhalte mit höherer Vertraulichkeit (z. B. die Bezeichnung "Vertraulich") ein Wasserzeichen und die Verschlüsselung aktiviert sein sollte.
3. **Veröffentlichen Sie die Bezeichnungen.** Nachdem Sie die Vertraulichkeitsbezeichnungen konfiguriert haben, können Sie sie mithilfe einer Bezeichnungsrichtlinie veröffentlichen. Legen Sie fest, welche Benutzer und Gruppen die Bezeichnungen haben sollen und welche Richtlinieneinstellungen verwendet werden. Eine einzelne Bezeichnung kann wiederverwendet werden. Sie definieren es einmal und können es dann in mehrere Bezeichnungsrichtlinien einschließen, die verschiedenen Benutzern zugewiesen sind.

Nachdem Sie Vertraulichkeitsbezeichnungen aus dem Microsoft 365 Compliance Center veröffentlicht haben, werden sie in [Office Apps](../compliance/sensitivity-labels-office-apps.md) angezeigt, damit Benutzer Inhalte so klassifizieren und schützen können, wie sie erstellt oder bearbeitet werden.

![Bereitstellungsfluss für Vertraulichkeitsbezeichnungen in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

Für den Datenschutz wenden Sie manuell eine Vertraulichkeitsbezeichnung mit Verschlüsselung und anderen Regeln auf E-Mails oder Inhalte mit vertraulichen persönlichen Informationen an.

> [!NOTE]
> Vertraulichkeitsbezeichnungen mit aktivierter Verschlüsselung, die auf E-Mails angewendet werden, weisen einige überlappende Funktionen mit OME auf. Siehe ["Sichere E-Mail-Szenarien" im Vergleich mit OME und Vertraulichkeitsbezeichnungen.](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Clientseitige automatische Bezeichnung, wenn Benutzer Dokumente bearbeiten oder E-Mails verfassen

Wenn Sie eine Vertraulichkeitsbezeichnung erstellen, können Sie diese Bezeichnung automatisch Inhalten einschließlich E-Mails [zuweisen,](../compliance/apply-sensitivity-label-automatically.md) wenn sie den von Ihnen angegebenen Bedingungen entsprechen.

Die Möglichkeit, Vertraulichkeitsbezeichnungen automatisch auf Inhalte anzuwenden, ist aus den folgenden Gründen wichtig:

- Sie müssen die Benutzer nicht schulen, damit sie alle Ihre Klassifizierungen kennen.
- Sie müssen sich nicht darauf verlassen, dass die Benutzer alle Inhalte richtig klassifizieren.
- Benutzer müssen nicht mehr über Ihre Richtlinien Bescheid wissen, sondern können sich stattdessen auf ihre Arbeit konzentrieren.

Die automatische Bezeichnung unterstützt das Empfehlen einer Bezeichnung für Benutzer sowie das automatische Anwenden einer Bezeichnung. In beiden Fällen entscheidet der Benutzer aber, ob die Bezeichnung angenommen oder abgelehnt werden soll, um die richtige Bezeichnung von Inhalten zu gewährleisten.

Diese clientseitige Beschriftung hat nur minimale Verzögerungen für Dokumente, da die Bezeichnung noch vor dem Speichern des Dokuments angewendet werden kann. Allerdings unterstützen nicht alle Client-Apps die automatische Bezeichnung. Diese Funktion wird vom Azure Information Protection-Client für einheitliche Bezeichnungen und [einigen Versionen von Office-Apps](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)unterstützt.

Konfigurationsanweisungen finden Sie unter [Konfigurieren der automatischen Bezeichnung für Office Apps.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

Aus Datenschutzgründen wenden Sie Vertraulichkeitsbezeichnungen automatisch auf Inhalte an, die vertrauliche persönliche Informationen enthalten.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Dienstseitige automatische Bezeichnung, wenn Inhalte bereits gespeichert sind

Diese Methode wird Autoklassifizierung mit Vertraulichkeitsbezeichnungen genannt. Möglicherweise wird es auch als automatische Bezeichnung für ruhenden Daten (für Dokumente in SharePoint und OneDrive) und Daten während der Übertragung (für E-Mails, die von Exchange gesendet oder empfangen werden) bezeichnet. Für Exchange werden keine E-Mails in ruhenden Postfächern eingeschlossen.

Da diese Bezeichnung vom Dienst selbst und nicht von der Benutzeranwendung angewendet wird, müssen Sie sich keine Gedanken darüber machen, welche Apps Benutzer haben und welche Version sie haben. Dies hat zur Folge, dass diese Funktion sofort in ihrer gesamten Organisation zur Verfügung steht, und sie eignet sich für Bezeichnungen jeder Größe. Richtlinien zum automatischen Bezeichnen unterstützen die empfohlene Bezeichnung nicht, da der Benutzer nicht mit dem Bezeichnungsprozess interagiert. Stattdessen führt der Administrator die Richtlinien im Simulationsmodus aus, um sicherzustellen, dass der Inhalt korrekt bezeichnet wird, bevor die Bezeichnung tatsächlich angewendet wird.

Konfigurationsanweisungen finden Sie unter Konfigurieren von Richtlinien für die [automatische Bezeichnung für SharePoint, OneDrive und Exchange.](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)

Um den Datenschutz auf betroffenen Websites zu gewährleisten, pushen Sie Vertraulichkeitsbezeichnungen für die automatische Verschlüsselung von Inhalten, die vertrauliche persönliche Informationen enthalten.

## <a name="data-loss-prevention"></a>Verhinderung von Datenverlust

Sie können [die Verhinderung von Datenverlust (Data Loss Prevention, DLP)](../compliance/dlp-learn-about-dlp.md) in Microsoft 365 verwenden, um riskante, unbeabsichtigte oder unangemessene Freigaben zu erkennen, zu warnen und zu blockieren, z. B. die interne und externe Freigabe von Daten, die personenbezogene Informationen enthalten.

DLP ermöglicht Folgendes:

- Identifizieren und überwachen Sie riskante Freigabeaktivitäten.
- Informieren Sie Die Benutzer mit Kontextanleitungen, um die richtigen Entscheidungen zu treffen.
- Erzwingen von Datennutzungsrichtlinien für Inhalte, ohne die Produktivität zu beeinträchtigen.
- Integration in Klassifizierung und Bezeichnung, um Daten zu erkennen und zu schützen, wenn sie freigegeben werden.

### <a name="supported-workloads-for-dlp"></a>Unterstützte Workloads für DLP

Mit einer DLP-Richtlinie im Microsoft 365 Compliance Center können Sie vertrauliche Elemente an vielen Orten in Microsoft 365 identifizieren, überwachen und automatisch schützen, z. B. Exchange Online, SharePoint, OneDrive und Microsoft Teams.

Sie können beispielsweise jedes Dokument identifizieren, das eine Kreditkartennummer enthält, die auf einer beliebigen OneDrive Website gespeichert ist, oder Sie können nur die OneDrive Websites bestimmter Personen überwachen.

Sie können vertrauliche Elemente auch in den lokal installierten Versionen von Excel, PowerPoint und Word überwachen und schützen, einschließlich der Möglichkeit, vertrauliche Elemente zu identifizieren und DLP-Richtlinien anzuwenden. DLP bietet eine kontinuierliche Überwachung, wenn Personen Inhalte aus diesen Office Apps freigeben.

> [!div class="mx-imgBorder"]
> ![Unterstützte Workloads für DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

Diese Abbildung zeigt ein Beispiel für den DLP-Schutz personenbezogener Daten.

> [!div class="mx-imgBorder"]
> ![Beispiel für den Schutz personenbezogener Daten mithilfe von DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP wird verwendet, um ein Dokument oder eine E-Mail mit einem Integritätseintrag zu identifizieren und dann automatisch den Zugriff auf dieses Dokument zu blockieren oder das Senden der E-Mail zu blockieren. DLP benachrichtigt dann den Empfänger mit einem Richtlinientipp und sendet eine Warnung an den Endbenutzer und Administrator.

### <a name="planning-for-dlp"></a>Planen von DLP

Planen Sie Ihre DLP-Richtlinien für:

- Ihre Geschäftlichen Anforderungen.

- Eine risikobasierte Bewertung der Organisation, wie im Artikel "Bewerten von [Datenschutzrisiken und Identifizieren vertraulicher Elemente"](information-protection-deploy-assess.md)beschrieben.

- Andere Informationsschutz- und Governance-Mechanismen, die in Kraft sind oder bei der Planung des Datenschutzes sind.

- Die Typen vertraulicher Informationen, die Sie basierend auf Ihrer Bewertungsarbeit für personenbezogene Daten identifiziert haben, wie im Artikel "Bewerten von [Datenschutzrisiken und Identifizieren vertraulicher Elemente"](information-protection-deploy-assess.md)beschrieben. DLP-Richtlinienbedingungen können sowohl auf Typen vertraulicher Informationen als auch auf Aufbewahrungsbezeichnungen basieren.

- Die Aufbewahrungsbezeichnungen, die Sie benötigen, um DLP-Bedingungen anzugeben. Weitere Informationen finden Sie im Artikel [zum Thema "Informationen zum Datenschutz" in Ihrer Organisation.](information-protection-deploy-govern.md)

- Fortlaufende DLP-Richtlinienverwaltung, bei der jemand in der Organisation Richtlinien für Änderungen an typen vertraulichen Informationen, Aufbewahrungsbezeichnungen, Vorschriften und Compliancerichtlinien ausführen und optimieren muss.

Obwohl Vertraulichkeitsbezeichnungen in DLP-Richtlinienbedingungen nicht verwendet werden können, sind bestimmte Schutzszenarien zum Verhindern des Zugriffs möglicherweise nur mit Vertraulichkeitsbezeichnungen erreichbar, die basierend auf vertraulichen Informationstypen automatisch angewendet werden können. Wenn eine robuste Vertraulichkeitsbezeichnung vorhanden ist, sollten Sie aus folgenden Gründen überlegen, ob DLP zur Verbesserung des Schutzes verwendet werden sollte:

  - DLP kann die Freigabe von Dateien verhindern. Vertraulichkeitsbezeichnungen können nur den Zugriff verhindern.

  - DLP verfügt über präzisere Steuerungsebenen in Bezug auf Regeln, Bedingungen und Aktionen.

  - DLP-Richtlinien können auf Teams Chat- und Kanalnachrichten angewendet werden. Vertraulichkeitsbezeichnungen können nur auf Dokumente und E-Mails angewendet werden.


### <a name="dlp-policies"></a>DLP-Richtlinien

DLP-Richtlinien werden im Microsoft Compliance Admin Center konfiguriert und geben den Schutzgrad, den vertraulichen Informationstyp, nach dem die Richtlinie sucht, und die Zielworkloads an. Ihre grundlegenden Komponenten bestehen aus der Identifizierung des Schutzes und der Datentypen.

> [!div class="mx-imgBorder"]
> ![DLP-Richtlinienkonfiguration in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

Hier ist ein Beispiel für eine DLP-Richtlinie zur Sensibilisierung für die DSGVO.

![Beispiel für eine DLP-Richtlinie zur Sensibilisierung für die DSGVO](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

Weitere Informationen zum Erstellen und Anwenden von DLP-Richtlinien finden Sie in [diesem Artikel.](../compliance/create-test-tune-dlp-policy.md)

### <a name="protection-levels-for-data-privacy"></a>Schutzebenen für den Datenschutz

In der folgenden Tabelle sind drei Konfigurationen zum Erhöhen des Schutzes mithilfe von DLP aufgeführt.

![Schutzebenen des Datenschutzes mit DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

Die erste Konfiguration, "Awareness", kann als Ausgangspunkt und Mindestschutz verwendet werden, um die Complianceanforderungen für Datenschutzbestimmungen zu erfüllen.

> [!NOTE]
> Mit dem erhöhten Schutzniveau nimmt die Fähigkeit der Benutzer, Informationen freizugeben und darauf zuzugreifen, in einigen Fällen ab und kann sich möglicherweise auf ihre Produktivität oder die Fähigkeit auswirken, tägliche Aufgaben auszuführen.

Um Ihren Mitarbeitern zu helfen, in einer sichereren Umgebung weiterhin produktiv zu sein, wenn sie die Schutzebene erhöhen, nehmen Sie sich Zeit, um sie in neuen Sicherheitsrichtlinien und -verfahren zu schulen und zu schulen.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Beispiel für die Verwendung von Vertraulichkeitsbezeichnungen mit DLP

Vertraulichkeitsbezeichnungen können mit DLP zusammenarbeiten, um Datenschutz in einer streng regulierten Umgebung bereitzustellen. Hier sind die wichtigsten Schritte der integrierten Bereitstellung:

1. Rechtliche und andere geschäftliche Anforderungen für den Datenschutz sind dokumentiert.
2. Zieldatenquellen, -typen und -besitz sind relativ zu Datenschutzbedenken gekennzeichnet.
3. Es wird eine allgemeine Strategie zum Erfüllen von Anforderungen und zum Schutz und zur Verwaltung von Datenschutz-Hotspots eingerichtet.
4. Ein stufenweiser Aktionsplan zur Behandlung der Datenschutzkontrollstrategie wird eingerichtet.

Sobald diese Elemente ermittelt wurden, können Sie vertrauliche Informationstypen, Ihre Taxonomie für Vertraulichkeitsbezeichnungen und DLP-Richtlinien zusammen verwenden. Diese Abbildung zeigt ein Beispiel.

> [!div class="mx-imgBorder"]
> ![Beispiel für Vertraulichkeitsbezeichnungen, die mit DLP arbeiten](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Anzeigen einer größeren Version dieses Bilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

Hier sind einige Datenschutzszenarien, in denen DLP und Vertraulichkeitsbezeichnungen zusammen verwendet werden, wie in der Abbildung dargestellt.

| Szenario | Prozess |
|:-------|:-----|
| A | <ol><li>Vertraulichkeitsbezeichnungen für Inhalte werden von einem Administrator für Benutzer und Gruppen zur manuellen oder automatischen Anwendung auf Inhalte und E-Mails veröffentlicht. </li><li>Benutzer A wendet die Bezeichnungen manuell oder automatisch an, wenn sie mit Inhalten interagieren, wobei Verschlüsselung oder andere Einstellungen angewendet werden. </li><li>Benutzer A sendet eine geschützte E-Mail oder Datei an Benutzer B, einen Gastbenutzer. </li></ol> |
| B | Die von einem Administrator für Benutzer A veröffentlichte DLP-Richtlinie verhindert, dass Benutzer A die E-Mail und/oder Datei an Benutzer B sendet. |
| C |  Die Vertraulichkeitsbezeichnung mit der Einstellung "Besitzer kann Gäste nicht einladen" wird für Benutzer A veröffentlicht, der ein Teams Team oder SharePoint Website angibt. Ein anderer Benutzer der Website versucht selektiv, eine Datei für Benutzer B freizugeben, aber DLP blockiert sie. |
| D | Die Vertraulichkeitsbezeichnung für die automatische Anwendung von Websiteinhalten wird auf einer oder mehreren Websites veröffentlicht, wodurch eine andere Schutzebene bereitgestellt wird, was zu einer geschützten Website führt. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>neue Funktionen für Office 365-Nachrichtenverschlüsselung (OME)

Personen verwenden E-Mails häufig, um vertrauliche Elemente auszutauschen, z. B. Patientenstatusinformationen oder Kunden- und Mitarbeiterinformationen. Die E-Mail-Nachrichtenverschlüsselung sorgt dafür, dass nur vorgesehene Empfänger verschlüsselte Nachrichten ansehen können.

Mit [OME](../compliance/ome.md)können Sie verschlüsselte Nachrichten zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen. OME arbeitet mit Outlook.com, Yahoo!, Gmail und anderen E-Mail-Diensten zusammen. OME trägt dazu bei, dass nur beabsichtigte Empfänger Nachrichteninhalte anzeigen können.

Für den Datenschutz verwenden Sie OME, um interne Nachrichten zu schützen, die vertrauliche Elemente enthalten. Office 365-Nachrichtenverschlüsselung ist ein Onlinedienst, der auf Microsoft Azure Rights Management (Azure RMS) basiert, der Teil von Azure Information Protection ist. Dies umfasst Verschlüsselungs-, Identitäts- und Autorisierungsrichtlinien, um Ihre E-Mails zu schützen. Sie können Nachrichten mithilfe von Rechteverwaltungsvorlagen, der Option "Nicht weiterleiten" und der Option "Nur verschlüsseln" verschlüsseln.

Sie können auch Nachrichtenflussregeln definieren, um diesen Schutz anzuwenden. Sie können z. B. eine Regel erstellen, die die Verschlüsselung aller Nachrichten erfordert, die an einen bestimmten Empfänger gerichtet sind oder die bestimmte Schlüsselwörter in der Betreffzeile enthält, und außerdem angeben, dass Empfänger den Inhalt der Nachricht nicht kopieren oder drucken können.

Darüber hinaus hilft Ihnen OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md) bei der Erfüllung von Compliance-Verpflichtungen, die flexiblere Kontrollen über externe Empfänger und deren Zugriff auf verschlüsselte E-Mails erfordern. Mit der erweiterten OME-Nachrichtenverschlüsselung in Microsoft 365 können Sie vertrauliche E-Mails, die außerhalb der Organisation freigegeben werden, mit automatischen Richtlinien steuern, die typen vertraulicher Informationen erkennen.

Wenn Sie E-Mails für den Datenschutz an eine externe Partei freigeben müssen, können Sie ein Ablaufdatum angeben und Nachrichten widerrufen. Sie können nur ein Ablaufdatum für Nachrichten widerrufen und festlegen, die an externe Empfänger gesendet werden.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Vergleich sicherer E-Mail-Szenarien mit OME und Vertraulichkeitsbezeichnungen

Da OME und Vertraulichkeitsbezeichnungen, die auf E-Mails mit Verschlüsselung angewendet werden, einige Überschneidungen aufweisen, ist es wichtig zu verstehen, für welche Szenarien beide gelten können, wie in dieser Tabelle dargestellt.

| Szenario | Vertraulichkeitsbezeichnungen | OME |
|:-------|:-----|:-------|
| Interne + Partner <br> Sichere Kommunikation und Zusammenarbeit zwischen internen Benutzern und vertrauenswürdigen Partnern | Empfehlen – Bezeichnungen mit vollständig angepasster Klassifizierung und Schutz | Ja – Nur verschlüsseln oder Schutz nicht weiterleiten ohne Klassifizierung |
| Externe Parteien <br> Sichere Kommunikation und Zusammenarbeit mit externen/Verbraucherbenutzern | Ja – vordefinierte Empfänger in Bezeichnung | Empfehlen – Just-in-Time-Schutz basierend auf Empfängern |
| Interne + Partner mit Ablauf/Sperrung <br> Steuern des Zugriffs auf E-Mails und Inhalte mit internen Benutzern und vertrauenswürdigen Partnern mit Ablauf und Sperrung | Empfehlung: Vollständig angepasster Schutz mit Zugriffsdauer, Benutzer können Dateien manuell nachverfolgen und widerrufen | Nein – kein Widerruf oder Ablauf für interne E-Mails |
| Externe Parteien mit Ablauf/Sperrung <br> Steuern des Zugriffs auf E-Mails und Inhalte mit externen/Verbraucherbenutzern mit Ablauf und Sperrung | Ja – Benutzer kann Dateien manuell nachverfolgen | Empfehlung (E5) – Der Administrator kann E-Mails aus dem Security & Compliance Center widerrufen. |
| Automatisches Bezeichnen <br> Die Organisation möchte E-Mails/Anlagen automatisch mit bestimmten vertraulichen Inhalten und/oder bestimmten Empfängern schützen. | Recommend (E5) – Automatisches Bezeichnen in Exchange und Outlook Clients, Erweiterung von Nachrichtenflussregeln und DLP-Richtlinie | Ja – Nachrichtenflussregeln und DLP-Richtlinie mit Nur verschlüsseln oder Schutz nicht weiterleiten |
||||

Zwischen diesen beiden Methoden gibt es auch Unterschiede bei der Endbenutzer- und Administratorerfahrung.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Teams mit Schutz für streng vertrauliche Daten

Informationen zu Organisationen, die beabsichtigen, personenbezogene Daten zu speichern, die den Datenschutzbestimmungen in Teams unterliegen, finden Sie unter ["Konfigurieren eines Teams mit Sicherheitsisolation",](secure-teams-security-isolation.md)das detaillierte Anleitungen und Konfigurationsschritte für Folgendes bereitstellt:

- Identitäts- und Gerätezugriff
- Erstellen eines privaten Teams
- Sperrung der zugrunde liegenden Berechtigungen für Teamwebsites
- Eine gruppenbasierte Vertraulichkeitsbezeichnung mit Verschlüsselung