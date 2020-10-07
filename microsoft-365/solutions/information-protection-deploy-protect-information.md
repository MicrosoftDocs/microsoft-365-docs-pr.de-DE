---
title: Schützen von Informationen unterliegen der Datenschutzverordnung
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
description: Bereitstellen von Sicherheits-und Compliance-Features von Microsoft 365 und Schützen Ihrer persönlichen Informationen.
ms.openlocfilehash: 97c34ca236ea4be98b9412518788630732259d5a
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377151"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Schützen von Informationen unterliegen der Datenschutzverordnung

In Ihrem Abonnement können eine Reihe von Informationen zum Schutz von Steuerelementen eingesetzt werden, um den Anforderungen und Bestimmungen zur Einhaltung von Datenschutzbestimmungen gerecht zu werden. Dazu gehören die allgemeine Datenschutzverordnung (dsgvo), HIPAA-HITECH (das United States Health Care Privacy Act), das California Consumer Protection Act (CCPA) und das Brazil Data Protection Act (LGPD).

Diese Steuerelemente befinden sich in den folgenden Lösungsbereichen:

- Vertraulichkeitsbezeichnungen
- Verhinderung von Datenverlusten (Data Loss Prevention, DLP)
- Office-Nachrichtenverschlüsselung (Office Message Encryption, OME)
- Zugriffssteuerung für Teams und Standorte

![Wichtige Dienste zum Schutz personenbezogener Informationen unterliegen der Datenschutzverordnung](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

>[!Note]
>In dieser Lösung werden Sicherheits-und Compliance-Features zum Schutz von Informationen unter Einhaltung der Datenschutzbestimmungen beschrieben. Eine vollständige Liste der Sicherheitsfeatures in Microsoft 365 finden Sie in der [Microsoft 365-Sicherheitsdokumentation](https://docs.microsoft.com/microsoft-365/security/). Eine vollständige Liste der Kompatibilitätsfeatures in Microsoft 365 finden Sie in der [Microsoft 365-Konformitäts Dokumentation](https://docs.microsoft.com/microsoft-365/compliance/).
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Datenschutzbestimmungen, die Auswirkungen auf den Informationsschutz haben

Im folgenden finden Sie eine Beispielliste der Datenschutzbestimmungen, die sich auf Informationen zum Schutz von Steuerelementen beziehen können:

- Dsgvo Artikel 5 Absatz 1 Buchstabe f)
- Dsgvo-Artikel (32) (1) (a)
- LGPD-Artikel 46
- HIPAA-HITECH (45 CFR 164.312 (e) (1))
- HIPAA-HITECH (45 C.F.R. 164.312 (e) (2) (II))

Weitere Informationen hierzu finden Sie im [Artikel bewerten von Datenschutzrisiken und Identifizieren von vertraulichen Elementen](information-protection-deploy-assess.md) .

Datenschutzbestimmungen für den Informationsschutz empfehlen:

- Schutz vor Verlust oder unbefugtem Zugriff, Nutzung und/oder Übertragung.
- Risikobasierte Anwendung von Schutzmechanismen.
- Verwendung der Verschlüsselung, falls zutreffend.

Ihre Organisation möchte möglicherweise auch Microsoft 365-Inhalte für andere Zwecke wie andere Compliance-Anforderungen oder aus geschäftlichen Gründen schützen. Das Einrichten Ihres Information Protection-Schemas für den Datenschutz sollte im Rahmen der Planung, Implementierung und Verwaltung des gesamten Informationsschutzes erfolgen.

Um Ihnen den Einstieg in ein Informationsschutz System in Microsoft 365 zu erleichtern, enthält der folgende Abschnitt eine kurze Liste der zugehörigen Funktionen und Verbesserungs Aktionen für Microsoft 365. Die Liste enthält Funktionen und Verbesserungs Aktionen, die auf Datenschutzbestimmungen anwendbar sind. Die Liste enthält jedoch keine älteren Technologien, wenn es eine neuere Funktion gibt, die die ältere Version weitgehend ersetzt. Beispielsweise ist die Verwaltung von Informationsrechten (Information Rights Management, IRM) für SharePoint und OneDrive nicht in der Liste enthalten, aber Vertraulichkeits Bezeichnungen sind enthalten.

## <a name="managing-information-protection-in-microsoft-365"></a>Verwalten des Informationsschutzes in Microsoft 365

Microsoft [Information Protection-Lösungen](../compliance/protect-information.md) umfassen eine Reihe integrierter Funktionen für Microsoft 365, Microsoft Azure und Microsoft Windows. In Microsoft 365 umfassen die Lösungen für den Informationsschutz Folgendes:

- [Dienstverschlüsselung mit dem Kundenschlüssel](../compliance/customer-key-overview.md)
- [Vertrauliche Informationstypen](../compliance/what-the-sensitive-information-types-look-for.md) (beschrieben im [Artikel bewerten von Datenschutzrisiken und identifizieren vertraulicher Elemente](information-protection-deploy-assess.md))
- [Vertraulichkeitsbezeichnungen](../compliance/sensitivity-labels.md) 
  - Dienst/Containerebene
  - Client seitige/inhaltsbasierte Ebene
  - Automatisiert für Daten-at-Rest in SharePoint und OneDrive
- Verhinderung von Datenverlust (Data Loss Prevention, DLP)
- [Microsoft 365 Endpunkt-Datenverlust Verhinderung (Vorschau)](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)
- [Office 365 Nachrichtenverschlüsselung neue Funktionen (OM)](../compliance/ome.md) und OM [Erweiterte Nachrichtenverschlüsselung](../compliance/ome-advanced-message-encryption.md)

Außerdem sind Schutz vor Website-und Bibliotheksebene wichtige Mechanismen, um in ein beliebiges Schutzschema einzubeziehen.

Informationen zu anderen Funktionen für den Informationsschutz außerhalb von Microsoft 365 finden Sie unter:

- [Microsoft Cloud Application Security (MCAS)](https://docs.microsoft.com/cloud-app-security/)
- [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Mithilfe von Sensitivitäts Bezeichnungen aus dem Microsoft Information Protection-Framework können Sie die Daten Ihrer Organisation klassifizieren und schützen, ohne die Produktivität der Benutzer und ihre Zusammenarbeit zu beeinträchtigen.

![Vertraulichkeits Bezeichnungen in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Voraussetzungen für Sensitivitäts Bezeichnungen

Führen Sie diese Aktivitäten vor der Implementierung einer der unten hervorgehobenen Sensitivitäts basierten Funktionen aus:

1. Grundlegendes zu folgenden Themen:
   - **Geschäftsanforderungen.** Legen Sie die geschäftlichen Gründe für das Anwenden von Sensitivitäts Bezeichnungen in Ihrem Unternehmen fest. Zum Beispiel Ihre Datenschutzanforderungen für den Informationsschutz.
   - **Empfindlichkeits Beschriftungsfunktionen.** Die Sensitivitäts Kennzeichnung kann komplex werden, daher sollten Sie vor dem ersten Start unbedingt die Dokumentation zu den [Sensitivitäts Bezeichnungen](../compliance/sensitivity-labels.md) lesen.
   - **Wichtige Dinge, die Sie beachten sollten** Vertraulichkeits Bezeichnungen werden im Microsoft Compliance Admin Center verwaltet, die Ausrichtungs-und Anwendungsoptionen variieren jedoch erheblich.
      - Es gibt Vertraulichkeits Bezeichnungen für Websites, Gruppen und Teams auf Containerebene (die Einstellungen gelten nicht für Inhalte im Container). Diese werden für Benutzer und Gruppen veröffentlicht, die Sie anwenden, wenn eine Website, eine Gruppe oder ein Team zur Verfügung gestellt wird.
      - Es gibt Sensitivitäts Bezeichnungen für aktive Inhalte. Diese werden auch für Benutzer oder Gruppen veröffentlicht, die Sie entweder manuell anwenden, oder Sie werden automatisch angewendet, wenn:
        - Die Datei wird entweder auf dem Desktop des Benutzers oder auf einer SharePoint-Website geöffnet/bearbeitet/gespeichert.
        - Eine e-Mail wird erstellt und gesendet.
      - Es gibt Vertraulichkeits Bezeichnungen für die automatische Anwendung in Dateien, die sich in Rest in SharePoint und OneDrive befinden, zusätzlich zu e-Mails in Transit über Exchange. Diese sind auf alle Websites oder bestimmte Ziele ausgerichtet und werden automatisch auf die in Ruhe stehenden Dateien in diesen Umgebungen angewendet.

2. Rationalisieren der aktuellen Sensitivitäts Kennzeichnung mit früheren oder alternativen Methoden

   - Azure Information Protection

      Das aktuelle Sensitivitäts Kennzeichnungs Schema muss möglicherweise mit einer vorhandenen [Azure Information Protection](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection) -Bezeichnungs Implementierung abgeglichen werden.
   - OME

      Wenn Sie die moderne Sensitivitäts Kennzeichnung für e-Mail-Schutz verwenden möchten und vorhandene e-Mail-Verschlüsselungsmethoden wie OM vorhanden sind, können Sie nebeneinander existieren, aber Sie sollten die Szenarien verstehen, in denen entweder angewendet werden sollte. Weitere Informationen finden Sie unter [Office 365 Nachrichtenverschlüsselung – neue Funktionen (OM)](#office-365-message-encryption-ome-new-capabilities), die eine Tabelle mit modernem Vertraulichkeitsschutz für Etikettentypen mit OM-basiertem Schutz enthält.

3. Planen der Integration in ein umfassenderes Informationsschutz Schema. Oben auf der Koexistenz mit OM können aktuelle Sensitivitäts Bezeichnungen neben Funktionen wie Microsoft 365 Data Loss Prevention (DLP) und Microsoft Cloud App Security verwendet werden. Weitere Informationen finden Sie unter [Sensitivitäts Bezeichnungen und Microsoft Cloud App Security](../compliance/sensitivity-labels.md#sensitivity-labels-and-microsoft-cloud-app-security) , um Ihre Datenschutzziele im Zusammenhang mit Datenschutz zu erreichen.

4. Entwickeln eines Klassifikations-und Steuerelement Schemas für die Sensitivitäts Bezeichnung. Siehe [Taxonomie von Datenklassifizierung und Sensitivitäts Bezeichnung](https://aka.ms/dataclassificationwhitepaper).

### <a name="general-guidance"></a>Allgemeine Hinweise

1. **Schema Definition.** Bevor Sie technische Funktionen zum Anwenden von Bezeichnungen und Schutz verwenden, müssen Sie in Ihrer Organisation ein Klassifikationsschema definieren. Möglicherweise verfügen Sie bereits über ein Klassifikationsschema, das das Hinzufügen personenbezogener Daten erleichtert. 
2. **Erste Schritte** Beginnen Sie mit der Entscheidung für die Anzahl und Namen der zu implementierenden Bezeichnungen. Führen Sie diese Aktivität aus, ohne sich Gedanken darüber machen zu müssen, welche Technologie verwendet werden soll und wie Beschriftungen angewendet werden. Wenden Sie dieses Schema universell in Ihrer Organisation an, einschließlich der Daten, die sich lokal und in anderen Cloud-Diensten befinden.
3. **Weitere Empfehlungen** Berücksichtigen Sie beim Entwerfen und Implementieren von Richtlinien, Bezeichnungen und Bedingungen die folgenden Empfehlungen:

   - **Verwenden Sie vorhandenes Klassifizierungsschema (sofern vorhanden).** Viele Organisationen verwenden bereits die Datenklassifizierung in irgendeiner Form. Werten Sie das vorhandene Bezeichnungsschema sorgfältig aus, und verwenden Sie es, wenn möglich, wie es ist. Durch die Verwendung vertrauter Bezeichnungen, die für Ihre Endbenutzer erkennbar sind, wird die Einführung vorangetrieben.
   - **Klein starten.** Es gibt praktisch keine Begrenzung für die Anzahl der Beschriftungen, die Sie erstellen können. Eine große Anzahl von Beschriftungen und unter Bezeichnungen kann die Einführung jedoch verlangsamen.
   - **Verwenden Sie Szenarien und Anwendungsfälle.** Identifizieren Sie häufige Anwendungsfälle in Ihrer Organisation, und verwenden Sie Szenarien, die von den Datenschutzbestimmungen abgeleitet sind, denen Sie unterliegen. Stellen Sie sicher, dass die Konfiguration für die festgestellten Bezeichnungen und die Klassifikation in der Praxis funktioniert.
   - **Stellen Sie jede Anforderung für eine neue Bezeichnung in Frage.** Benötigen alle Szenarien oder Anwendungsfälle wirklich eine neue Bezeichnung oder können Sie das bereits verwendete verwenden? Wenn die Anzahl der Beschriftungen minimal bleibt, wird die Einführung verbessert.
   - **Verwenden Sie unter Bezeichnungen für wichtige Abteilungen.** Einige Abteilungen haben spezifische Anforderungen, die bestimmte Bezeichnungen erfordern. Definieren Sie diese Bezeichnungen als unter Bezeichnungen für eine vorhandene Bezeichnung, und verwenden Sie dann bereichsbasierte Richtlinien, die Benutzergruppen statt Global zugewiesen sind.
   - **Prüfen Sie die bereichsbezogenen Richtlinien.** Richtlinien, die auf Teilmengen von Benutzern abzielen, verhindern eine Bezeichnungs Überlastung. Eine bereichsbezogene Richtlinie ermöglicht das Zuweisen von Rollen-oder abteilungsspezifischen Beschriftungen oder unter Bezeichnungen nur für Mitarbeiter, die für diese bestimmte Abteilung arbeiten. 
   - **Verwenden Sie aussagekräftige Bezeichnungen.** Versuchen Sie nicht, Jargon, Standards oder Akronyme als Bezeichnungsnamen zu verwenden. Versuchen Sie, Namen zu verwenden, die mit dem Endbenutzer in Resonanz stehen, um die Einführung zu verbessern. Statt Bezeichnungen wie PII, PCI, HIPAA, LBI, MBI und HBI zu verwenden, sollten Sie Namen wie nicht geschäftliche, öffentliche, allgemeine, vertrauliche und streng vertraulich behandeln.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Erstellen und Bereitstellen von Sensitivitäts Bezeichnungen für Websites, Gruppen und Teams

Wenn Sie [Sensitivitäts Bezeichnungen](../compliance/sensitivity-labels-teams-groups-sites.md) im Microsoft 365 Compliance Center erstellen, können Sie diese nun auf diese Container anwenden:

- Microsoft Teams-Websites
- Microsoft 365-Gruppen (früher Office 365 Gruppen)
- SharePoint-Websites

Verwenden Sie die folgenden Bezeichnungseinstellungen zum Schutz von Inhalt in diesen Containern:

- Datenschutz (öffentlich oder privat) von Microsoft 365-Websites mit Gruppen verbundenen Teams
- Zugriff durch externe Benutzer
- Zugriff von nicht verwalteten Geräten aus

Um die externe Freigabe für Container zu verhindern, die zum Speichern von Inhalten mit vertraulichen personenbezogenen Daten verwendet werden, markieren Sie die Dateien, die die Daten enthalten, als privat und erfordern verwaltete Geräte.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Erstellen und Bereitstellen von Sensitivitäts Bezeichnungen für Inhalte

Auf Dateien angewendete Sensitivitäts Bezeichnungen ermöglichen es Ihnen, ihre Inhalte zu verschlüsseln, das Wasserzeichen für den Inhalt zu kennzeichnen und andere Steuerelemente für Office-Anwendungsinhalte zu definieren, einschließlich Outlook und Office im Internet.

Wenn Sie mit dem Schutz der Daten Ihrer Organisation mit Vertraulichkeits Bezeichnungen beginnen möchten, können Sie Folgendes tun:

1. **Erstellen Sie die Bezeichnungen.** Erstellen und benennen Sie Ihre Vertraulichkeitsbezeichnungen gemäß der Klassifizierungstaxonomie Ihrer Organisation für unterschiedliche Vertraulichkeitsstufen von Inhalten. Weitere Informationen zum Entwickeln einer Klassifizierungs Taxonomie finden Sie im [White Paper Taxonomie für Datenklassifizierung und Sensitivitäts Kennzeichnung](https://aka.ms/dataclassificationwhitepaper).
2. **Legen Sie fest, wozu jede einzelne Bezeichnung dient.** Konfigurieren Sie die Schutzeinstellungen, die mit den einzelnen Bezeichnungen verknüpft werden sollen. Möglicherweise möchten Sie, dass für niedrigere Vertraulichkeits Inhalte (beispielsweise eine "allgemeine" Bezeichnung) nur eine Kopf-oder Fußzeile angewendet wird, während höhere Empfindlichkeits Inhalte (beispielsweise eine "vertrauliche" Bezeichnung) über ein Wasserzeichen verfügen und die Verschlüsselung aktiviert ist.
3. **Veröffentlichen Sie die Bezeichnungen.** Nachdem Sie die Vertraulichkeitsbezeichnungen konfiguriert haben, können Sie sie mithilfe einer Bezeichnungsrichtlinie veröffentlichen. Legen Sie fest, welche Benutzer und Gruppen die Bezeichnungen haben sollen und welche Richtlinieneinstellungen verwendet werden. Eine einzelne Bezeichnung ist wieder verwendbar. Sie können es einmal definieren und dann in mehrere Bezeichnungsrichtlinien einbeziehen, die verschiedenen Benutzern zugewiesen sind.

Nachdem Sie Sensitivitäts Bezeichnungen im Microsoft 365 Compliance Center veröffentlicht haben, werden Sie in [Office-Apps](../compliance/sensitivity-labels-office-apps.md) angezeigt, damit Benutzer Inhalte klassifizieren und schützen können, wenn Sie erstellt oder bearbeitet werden.

![Bereitstellungs Fluss für Sensitivitäts Bezeichnungen in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

Für den Datenschutz wenden Sie eine Vertraulichkeits Bezeichnung mit Verschlüsselung und anderen Regeln auf e-Mails oder Inhalte mit vertraulichen personenbezogenen Informationen manuell an.

>[!Note]
>Vertraulichkeits Bezeichnungen mit aktivierter Verschlüsselung für e-Mails weisen einige überlappende Funktionen mit OM auf. Weitere Informationen finden Sie unter [Secure Mail Scenarios comparison with OM and Sensitivity Labels](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels).

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Client seitige automatische Kennzeichnung, wenn Benutzer Dokumente bearbeiten oder e-Mails verfassen

Wenn Sie eine Vertraulichkeits Bezeichnung erstellen, können Sie [diese Bezeichnung automatisch](../compliance/apply-sensitivity-label-automatically.md) Inhalten einschließlich e-Mail zuweisen, wenn Sie Bedingungen übereinstimmen, die Sie angeben.

Die Möglichkeit, Vertraulichkeitsbezeichnungen automatisch auf Inhalte anzuwenden, ist aus den folgenden Gründen wichtig:

- Sie müssen die Benutzer nicht schulen, damit sie alle Ihre Klassifizierungen kennen.
- Sie müssen sich nicht darauf verlassen, dass die Benutzer alle Inhalte richtig klassifizieren.
- Benutzer müssen nicht mehr über Ihre Richtlinien Bescheid wissen, sondern können sich stattdessen auf ihre Arbeit konzentrieren.

Die automatische Beschriftung unterstützt die Empfehlung einer Bezeichnung für Benutzer sowie die automatische Anwendung einer Bezeichnung. In beiden Fällen entscheidet der Benutzer aber, ob die Bezeichnung angenommen oder abgelehnt werden soll, um die richtige Bezeichnung von Inhalten zu gewährleisten.

Diese clientseitige Beschriftung hat nur minimale Verzögerungen für Dokumente, da die Bezeichnung noch vor dem Speichern des Dokuments angewendet werden kann. Allerdings unterstützen nicht alle Client-Apps die automatische Bezeichnung. Diese Funktion wird vom Azure Information Protection Unified Labeling-Client und [einigen Versionen von Office-Apps](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)unterstützt.

Konfigurationsanweisungen finden Sie unter [Konfigurieren der automatischen Bezeichnungs Funktion für Office-Apps](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Für den Datenschutz verwenden Sie automatisch Vertraulichkeits Bezeichnungen für Inhalte mit vertraulichen personenbezogenen Informationen.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Dienstseitige automatische Kennzeichnung beim bereits gespeicherten Inhalt

Diese Methode wird Autoklassifizierung mit Vertraulichkeitsbezeichnungen genannt. Sie hören möglicherweise auch, dass Sie als automatische Benennung von Daten im Ruhezustand (für Dokumente in SharePoint und OneDrive) und Daten in der Übertragung (für e-Mails, die von Exchange gesendet oder empfangen werden) bezeichnet werden. Für Exchange enthält es keine e-Mails in Postfächern in Ruhe.
 
Da diese Bezeichnung vom Dienst selbst angewendet wird und nicht von der Benutzeranwendung, müssen Sie sich keine Gedanken darüber machen, was apps-Benutzer haben und welche Version. Dies hat zur Folge, dass diese Funktion sofort in ihrer gesamten Organisation zur Verfügung steht, und sie eignet sich für Bezeichnungen jeder Größe. Richtlinien zum automatischen Bezeichnen unterstützen die empfohlene Bezeichnung nicht, da der Benutzer nicht mit dem Bezeichnungsprozess interagiert. Stattdessen führt der Administrator die Richtlinien im Simulationsmodus aus, um sicherzustellen, dass der Inhalt korrekt bezeichnet wird, bevor die Bezeichnung tatsächlich angewendet wird.

Konfigurationsanweisungen finden Sie unter [Konfigurieren von Richtlinien für die automatische Bezeichnungsrichtlinie für SharePoint, OneDrive und Exchange](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange).

Für den Datenschutz innerhalb von Websites von Concern, Push-Empfindlichkeits Bezeichnungen für die automatische Verschlüsselung von Inhalten mit vertraulichen personenbezogenen Informationen.

## <a name="data-loss-prevention"></a>Verhinderung von Datenverlust 

Sie können die [Datenverlust Verhinderung (Data Loss Prevention, DLP)](../compliance/data-loss-prevention-policies.md) in Microsoft 365 verwenden, um eine riskante, unbeabsichtigte oder ungeeignete Freigabe zu erkennen, zu warnen oder zu blockieren, beispielsweise die Freigabe von Daten, die persönliche Informationen enthalten, sowohl intern als auch extern.

DLP ermöglicht Folgendes:

- Identifizieren und überwachen riskanter freigabeaktivitäten.
- Informieren Sie Benutzer mit kontextbezogenen Anleitungen, um die richtigen Entscheidungen zu treffen.
- Erzwingen von Daten Nutzungsrichtlinien bei Inhalten ohne Produktivitätseinbußen
- Integration mit Klassifizierung und Kennzeichnung zum erkennen und schützen von Daten, wenn diese freigegeben werden.

### <a name="supported-workloads-for-dlp"></a>Unterstützte Arbeitsauslastungen für DLP

Mit einer DLP-Richtlinie im Microsoft 365 Compliance Center können Sie vertrauliche Elemente in Microsoft 365 wie Exchange Online, SharePoint, OneDrive und Microsoft Teams über mehrere Standorte hinweg identifizieren, überwachen und automatisch schützen.

Sie können beispielsweise jedes Dokument identifizieren, das eine Kreditkartennummer enthält, die in einer beliebigen OneDrive-Website gespeichert ist, oder Sie können nur die OneDrive-Websites bestimmter Personen überwachen.

Sie können auch vertrauliche Elemente in den lokal installierten Versionen von Excel, PowerPoint und Word überwachen und schützen, einschließlich der Fähigkeit, vertrauliche Elemente zu identifizieren und DLP-Richtlinien anzuwenden. DLP bietet eine kontinuierliche Überwachung, wenn Personen Inhalte aus diesen Office-Apps freigeben.

![Unterstützte Arbeitsauslastungen für DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

Diese Abbildung zeigt ein Beispiel für den DLP-Schutz personenbezogener Daten.

![Beispiel für den Schutz personenbezogener Daten mithilfe von DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP wird verwendet, um ein Dokument oder eine e-Mail mit einem Integritäts Eintrag zu identifizieren und dann den Zugriff auf dieses Dokument automatisch zu blockieren oder die e-Mail-Nachricht zu blockieren. DLP benachrichtigt dann den Empfänger mit einem richtlinientipp und sendet eine Warnung an den Endbenutzer und den Administrator.

### <a name="planning-for-dlp"></a>Planen von DLP

Planen Sie Ihre DLP-Richtlinien für: 

- Ihre geschäftlichen Anforderungen.

- Eine risikobasierte Bewertung der Organisation, wie im [Artikel bewerten von Datenschutzrisiken und identifizieren vertraulicher Elemente](information-protection-deploy-assess.md)beschrieben.

- Andere Mechanismen für den Schutz und die Steuerung des Datenschutzes oder die Planung des Datenschutzes.

- Die Typen vertraulicher Informationen, die Sie basierend auf ihren Bewertungen für personenbezogene Daten identifiziert haben, funktionieren wie im [Artikel bewerten von Datenschutzrisiken und identifizieren vertraulicher Elemente](information-protection-deploy-assess.md)beschrieben. DLP-Richtlinienbedingungen können sowohl auf vertraulichen Informationstypen als auch auf Aufbewahrungs Bezeichnungen basieren.

- Die Aufbewahrungs Bezeichnungen, die Sie zum Angeben von DLP-Bedingungen benötigen. Weitere Informationen finden Sie unter [Informationen zum Datenschutz in Ihrem Unternehmens](information-protection-deploy-govern.md) -Artikel "Richtlinie".

- Laufende DLP-Richtlinienverwaltung, für die eine Person in der Organisation Richtlinien für Änderungen an vertraulichen Informationstypen, Aufbewahrungs Bezeichnungen, Verordnungen und Konformitätsrichtlinien verarbeiten und optimieren muss.

Obwohl Vertraulichkeits Bezeichnungen nicht in DLP-Richtlinienbedingungen verwendet werden können, können bestimmte Schutz Szenarien zum Verhindern des Zugriffs möglicherweise nur mit Sensitivitäts Bezeichnungen erreicht werden, die basierend auf vertraulichen Informationstypen automatisch angewendet werden können. Wenn eine robuste Sensitivitäts Kennzeichnung vorhanden ist, sollten Sie prüfen, ob DLP verwendet werden sollte, um den Schutz zu erhöhen, da:

  - DLP kann die Freigabe von Dateien verhindern. Vertraulichkeits Bezeichnungen können den Zugriff einfach verhindern.

  - DLP verfügt über präzisere Steuerungsebenen hinsichtlich Regeln, Bedingungen und Aktionen.

  - DLP-Richtlinien können auf Microsoft Teams-Chat-und Kanal Nachrichten angewendet werden. Vertraulichkeits Bezeichnungen können nur auf Dokumente und e-Mails angewendet werden.


### <a name="dlp-policies"></a>DLP-Richtlinien

DLP-Richtlinien werden im Microsoft Compliance Admin Center konfiguriert und geben den Schutzgrad, den Typ der vertraulichen Informationen, den die Richtlinie sucht, und die Ziel Arbeitsauslastungen an. Ihre grundlegenden Komponenten bestehen darin, den Schutz und die Datentypen zu identifizieren.

![DLP-Richtlinienkonfiguration in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

Im folgenden finden Sie ein Beispiel für eine DLP-Richtlinie zur Sensibilisierung für dsgvo.

![Beispiel für eine DLP-Richtlinie für das Bewusstsein für dsgvo](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

Weitere Informationen zum Erstellen und Anwenden von DLP-Richtlinien finden Sie in [diesem Artikel](../compliance/create-test-tune-dlp-policy.md) .

### <a name="protection-levels-for-data-privacy"></a>Schutzebenen für den Datenschutz

In der folgenden Tabelle sind drei Konfigurationen für den wachsenden Schutz mit DLP aufgeführt.

![Schutzebenen des Datenschutzes mit DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

Die erste Konfiguration, das Bewusstsein, kann als Ausgangspunkt und Mindestschutz für die Erfüllung der Compliance-Anforderungen für Datenschutzbestimmungen verwendet werden.

>[!Note]
>Wenn sich die Schutzniveaus erhöhen, verringert sich in einigen Fällen die Fähigkeit von Benutzern, Informationen freizugeben und auf diese zuzugreifen, und es kann möglicherweise Auswirkungen auf die Produktivität oder die Möglichkeit zum Ausführen von täglichen Aufgaben haben.
>

Damit Ihre Mitarbeiter weiterhin in einer sichereren Umgebung produktiv arbeiten können, wenn Sie die Schutzebenen erhöhen, sollten Sie sich die Zeit nehmen, Sie in neuen Sicherheitsrichtlinien und-Verfahren auszubilden und zu Schulen.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Beispiel für die Verwendung von Sensitivitäts Bezeichnungen mit DLP

Vertraulichkeits Bezeichnungen können mit DLP zusammenarbeiten, um den Datenschutz in einer stark regulierten Umgebung bereitzustellen. Im folgenden finden Sie die wichtigsten Schritte der integrierten Bereitstellung:

1. Regulatorische und anderweitige geschäftliche Anforderungen für den Datenschutz werden dokumentiert.
2. Zieldatenquellen,-Typen und-Besitz sind im Verhältnis zu Datenschutzaspekten charakterisiert.
3. Eine Gesamtstrategie zur Behebung von Anforderungen und zum Schutz und zur Steuerung der Datenschutz-Hotspots wird hergestellt.
4. Ein Phasenbasierter Aktionsplan zur Behandlung der Datenschutz-Steuerungsstrategie wird eingeführt.

Nachdem diese Elemente bestimmt wurden, können Sie vertrauliche Informationstypen, ihre Sensitivitäts Bezeichnung für die Taxonomie und DLP-Richtlinien zusammen verwenden. Diese Abbildung zeigt ein Beispiel.

![Beispiel für Sensitivitäts Bezeichnungen, die mit DLP arbeiten](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Anzeigen einer größeren Version dieses Bilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

Hier sind einige Datenschutzszenarien, in denen DLP und Sensitivitäts Bezeichnungen zusammen verwendet werden, wie in der Abbildung dargestellt.

| Szenario | Prozess |
|:-------|:-----|
| A | <ol><li>Vertraulichkeits Bezeichnungen für Inhalte werden von einem Administrator für Benutzer und Gruppen zur manuellen oder automatischen Anwendung in Inhalt und e-Mail veröffentlicht. </li><li>Benutzer A wendet die Beschriftungen manuell oder automatisch an, wenn Sie mit Inhalten interagieren, wobei Verschlüsselung oder andere Einstellungen angewendet werden. </li><li>Benutzer a sendet eine geschützte e-Mail oder Datei an Benutzer B, einen Gastbenutzer. </li></ol> |
| B | DLP-Richtlinie, die von einem Administrator veröffentlicht wurde, um Benutzer a zu blockieren, dass Benutzer a die e-Mail und/oder Datei an Benutzer B sendet. |
| C |  Vertraulichkeits Bezeichnung mit der Einstellung "Besitzer kann keine Gäste einladen" wird für Benutzer a veröffentlicht, der ein Teams-Team oder eine SharePoint-Website bereitstellt. Ein anderer Benutzer der Website versucht selektiv, eine Datei mit Benutzer B freizugeben, aber DLP blockiert Sie. |
| D | Vertraulichkeits Bezeichnung für die automatische Anwendung auf Websiteinhalte werden auf einer oder mehreren Websites veröffentlicht und bieten eine weitere Schutzebene, was zu einer geschützten Website führt. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Neue Funktionen für Office 365 Nachrichtenverschlüsselung (OM)

Benutzer verwenden häufig e-Mails zum Austauschen vertraulicher Elemente, beispielsweise Informationen zur Patienten Integrität oder Informationen zu Kunden und Mitarbeitern. Die E-Mail-Nachrichtenverschlüsselung sorgt dafür, dass nur vorgesehene Empfänger verschlüsselte Nachrichten ansehen können.

Mit [OM](../compliance/ome.md)können Sie verschlüsselte Nachrichten zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen. OM kann mit Outlook.com, Yahoo!, Gmail und anderen e-Mail-Diensten verwendet werden. OM hilft sicherzustellen, dass nur vorgesehene Empfänger Nachrichteninhalte anzeigen können.

Für den Datenschutz verwenden Sie OM, um interne Nachrichten mit vertraulichen Elementen zu schützen. Office 365 Nachrichtenverschlüsselung ist ein Onlinedienst, der auf Microsoft Azure Rights Management (Azure RMS) basiert, das Teil von Azure Information Protection ist. Dies umfasst Verschlüsselungs-, Identitäts-und Autorisierungsrichtlinien, um Ihre e-Mails zu schützen. Sie können Nachrichten mithilfe von Vorlagen für die Rechteverwaltung, der Option "nicht weiterleiten" und der Option "nur verschlüsseln" verschlüsseln.

Sie können auch e-Mail-Flussregeln definieren, um diesen Schutz anzuwenden. Sie können beispielsweise eine Regel erstellen, die die Verschlüsselung aller an einen bestimmten Empfänger adressierten Nachrichten erfordert oder die bestimmte Schlüsselwörter in der Betreffzeile enthält, und auch angeben, dass Empfänger den Inhalt der Nachricht nicht kopieren oder ausdrucken können.

Darüber hinaus hilft Ihnen die [Advanced-Nachrichtenverschlüsselung](../compliance/ome-advanced-message-encryption.md) bei der Erfüllung von Compliance-Verpflichtungen, die flexiblere Kontrollen externer Empfänger und deren Zugriff auf verschlüsselte e-Mails erfordern. Mit der erweiterten OM-Nachrichtenverschlüsselung in Microsoft 365 können Sie vertrauliche e-Mails, die außerhalb der Organisation freigegeben werden, mit automatischen Richtlinien steuern, mit denen vertrauliche Informationstypen erkannt werden. 

Wenn Sie e-Mails für eine externe Person freigeben müssen, können Sie für den Datenschutz ein Ablaufdatum angeben und Nachrichten widerrufen. Sie können ein Ablaufdatum für Nachrichten, die an externe Empfänger gesendet werden, nur widerrufen und festlegen.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Sichere e-Mail-Szenarien im Vergleich zu OM und Sensitivitäts Bezeichnungen

OM-und Sensitivitäts Bezeichnungen, die auf e-Mails mit Verschlüsselung angewendet werden, haben einige Überschneidungen, daher ist es wichtig zu verstehen, welche Szenarien für welche zutreffen, wie in dieser Tabelle dargestellt.

| Szenario | Vertraulichkeits Bezeichnungen | OME |
|:-------|:-----|:-------|
| Interne + Partner <br> Sicheres kommunizieren und zusammenarbeiten zwischen internen Benutzern und vertrauenswürdigen Partnern | Empfehlen – Beschriftungen mit vollständig angepasster Klassifizierung und Schutz | Ja – nur Verschlüsselung oder keine Weiterleitung des Schutzes ohne Klassifizierung |
| Externe Parteien <br> Sicheres kommunizieren und zusammenarbeiten mit externen/Consumer-Benutzern | Yes – Empfänger in der Bezeichnung vordefinieren | Empfehlen – Just-in-Time-Schutz basierend auf Empfängern |
| Interne + Partner, mit Ablauf/Widerruf <br> Steuern des Zugriffs auf e-Mails und Inhalte mit internen Benutzern und vertrauenswürdigen Partnern mit Ablauf und Sperrung | Empfehlen – vollständig angepasster Schutz mit Zugriffsdauer, Benutzer kann Dateien manuell nachverfolgen und widerrufen | Nein – kein Widerruf oder Ablauf für interne e-Mails |
| Externe Parteien mit Ablauf/Widerruf <br> Steuern des Zugriffs von e-Mails und Inhalten mit externen Benutzern/Consumern mit Ablauf und Sperrung | Ja – Benutzer kann Dateien manuell nachverfolgen | Recommend (E5) – der Administrator kann e-Mails vom Security & Compliance Center widerrufen. |
| Automatisches Bezeichnen <br> Organisation möchte automatisch e-Mail-Anlagen mit bestimmten vertraulichen Inhalten und/oder bestimmten Empfängern schützen. | Recommend (E5) – automatische Kennzeichnung in Exchange-und Outlook-Clients, erweiterte Nachrichtenfluss Regeln und DLP-Richtlinie | Ja-Nachrichtenfluss Regeln und DLP-Richtlinie mit nur verschlüsseln oder nicht Weiterleitungs Schutz |
||||

Es gibt auch Unterschiede bei den Benutzer-und Administrator-Erfahrungen zwischen diesen beiden Methoden.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Teams mit Schutz für hoch vertrauliche Daten

Organisationen, in denen personenbezogene Daten in Microsoft Teams unter den Datenschutzbestimmungen gespeichert werden sollen, finden Sie unter [Konfigurieren eines Teams mit Sicherheitsisolierung](secure-teams-security-isolation.md), das detaillierte Anleitungen und Konfigurationsschritte für die folgenden Schritte bereitstellt:

- Identitäts- und Gerätezugriff
- Erstellen eines privaten Teams
- Sperrung der zugrunde liegenden Teamwebsite Berechtigungen
- Eine Gruppenbasierte Sensitivitäts Bezeichnung mit Verschlüsselung
