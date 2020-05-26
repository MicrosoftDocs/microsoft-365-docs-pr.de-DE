---
title: Planen der Gruppensteuerung
ms.reviewer: johasand
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BSA160
description: Hier erfahren Sie, wie Sie Microsoft 365 Groups Governance planen.
ms.openlocfilehash: c37f88cbd3f41f22c1effdd7ba482033012aff01
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351839"
---
# <a name="plan-for-governance-in-groups"></a>Planen der Steuerung in Gruppen

Microsoft 365 Groups verfügt über eine Vielzahl von Tools zur Implementierung von Steuerungsfunktionen, die Ihre Organisation möglicherweise benötigt. Dieser Artikel leitet IT-Experten an, die richtigen Fragen zu stellen, um ihre Anforderungen an die Governance zu ermitteln und zu bestimmen, wie sie diese auf der Grundlage ihres organisatorischen Profils erfüllen können.

## <a name="why-microsoft-365-groups"></a>Gründe für Microsoft 365-Gruppen
![Bildbeschreibung](../../media/01.png)

Wir wissen, dass Organisationen heute ein vielfältiges Toolset verwenden. Es gibt das Entwicklerteam, das Team Chats verwendet, die Führungskräfte, die e-Mails senden, und die gesamte Organisation, die über Enterprise Social eine Verbindung herstellt. Es werden mehrere Tools für die Zusammenarbeit verwendet, da jede Gruppe einzigartig ist und ihre eigenen funktionalen Bedürfnisse und ihren eigenen Arbeitsstil hat. Einige werden nur E-Mail verwenden, während andere hauptsächlich im Chat leben. 

Wenn Benutzer das Gefühl haben, dass die von der IT angebotenen Tools nicht ihren Bedürfnissen entsprechen, werden sie wahrscheinlich ihre bevorzugte Verbraucheranwendung herunterladen, die ihre Szenarien unterstützt. Obwohl dieser Prozess den Benutzern einen schnellen Einstieg ermöglicht, führt er zu einer frustrierenden Benutzererfahrung in der gesamten Organisation mit mehreren Anmeldungen, gemeinsamer Nutzung von Schwierigkeiten und keinem einzigen Ort zum Anzeigen von Inhalten. Dieses Konzept wird als "Shadow IT" bezeichnet und stellt ein erhebliches Risiko für Organisationen dar. Es reduziert die Möglichkeit, den Benutzerzugriff einheitlich zu verwalten, die Sicherheit zu gewährleisten und die Anforderungen an die Einhaltung von Diensten zu erfüllen.

Microsoft 365-Gruppen ermächtigen Benutzer und verringern das Risiko von Shadow IT, indem Sie in einem einzigen Schritt viele der Tools bereitstellen, die für die Zusammenarbeit erforderlich sind. In Microsoft 365-Gruppen können Sie eine Gruppe von Personen auswählen, mit denen Sie zusammenarbeiten möchten, und einfach eine Sammlung von Ressourcen einrichten, die von diesen Personen gemeinsam genutzt werden können. Das manuelle Zuweisen von Berechtigungen zu Ressourcen gehört der Vergangenheit an, da das Hinzufügen von Mitgliedern zur Gruppe automatisch die erforderlichen Berechtigungen für alle von der Gruppe bereitgestellten Objekte gewährt.

## <a name="technical-architecture"></a>Technische Architektur

Es gibt drei Haupt Kommunikationsmethoden, die von Microsoft 365-Gruppen unterstützt werden. Gruppen können in diesen Erfahrungen erstellt und in Microsoft 365 verwendet werden:
- Outlook: Zusammenarbeit per E-Mail mit einem freigegebenen Gruppenposteingang und Kalender
- Microsoft Teams: ein beständiger Chat-basierter Arbeitsbereich, in dem Sie informelle, echt zeitbezogene Unterhaltungen zu einer Vielzahl von Themen haben können, die von bestimmten Untergruppen organisiert werden.
- Yammer: unternehmerische soziale Netzwerke für die Zusammenarbeit

> [!NOTE]
> Durch das Erstellen einer neuen Gruppe über andere Teamarbeits Anwendungen wie SharePoint, Planner oder Stream wird eine Gruppe mit einem Outlook-Posteingang erstellt und die Möglichkeit zum Herstellen einer Verbindung mit Microsoft Teams hergestellt.

Je nachdem, wo eine Gruppe erstellt wird, werden bestimmte Ressourcen automatisch bereitgestellt, beispielsweise:
- [Posteingang](https://support.microsoft.com/en-us/office/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) -für e-Mail-Unterhaltungen zwischen Gruppenmitgliedern. Dieser Posteingang hat eine E-Mail-Adresse und kann für das Annehmen von Nachrichten von Personen außerhalb der Gruppe und sogar außerhalb Ihrer Organisation konfiguriert werden, ähnlich wie eine herkömmliche Verteilerliste.
 - [Kalender](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) – Für die Planung von Ereignissen im Zusammenhang mit der Gruppe
- [SharePoint-Teamwebsite](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) – ein zentrales Repository für Informationen, Links und Inhalte im Zusammenhang mit Ihrer Gruppe
- [SharePoint-Dokumentbibliothek](https://support.microsoft.com/en-us/office/share-group-files-in-outlook-749bc73b-90c9-4760-9b6f-9aa1cf01b403) – ein zentraler Ort für die Gruppe zum Speichern und Freigeben von Dateien
- [OneNote-Notizbuch](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) – zum Sammeln von Ideen, Recherchen und Informationen
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) – Für das Zuweisen und Verwalten von Projektaufgaben für die Mitglieder Ihrer Gruppe
- [Gruppe "jammern"](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) – ein allgemeiner Ort für Unterhaltungen und Freigabe Informationen
- Microsoft Teams – ein Chat basierter Arbeitsbereich in Microsoft 365

Weitere Informationen darüber, welche Ressourcen für die einzelnen Gruppen erstellt werden, finden Sie unter [Informationen zu Microsoft 365-Gruppen](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

> [!NOTE]
> Wenn eine neue Microsoft 365-Gruppe über "jammern" oder "Teams" erstellt wird, ist die Gruppe in Outlook oder im Adressbuch nicht sichtbar, da die primäre Kommunikation zwischen diesen Benutzern in ihren jeweiligen Clients erfolgt. Jammern von Gruppen kann nicht mit Microsoft Teams verbunden werden.

## <a name="where-to-start-a-conversation"></a>Wo man eine Unterhaltung beginnt
Es gibt mehrere Orte für eine Unterhaltung in Microsoft 365. Das Verstehen, wo man eine Unterhaltung beginnt, kann Organisationen helfen, eine Kommunikationsstrategie zu definieren.

![Bildbeschreibung](../../media/03.png)

- Teams: Chat-basierter Arbeitsbereich (Zusammenarbeit mit hoher Geschwindigkeit) – innere Schleife
   - Entwickelt für die Zusammenarbeit mit den Personen, mit denen Sie täglich arbeiten
  - Stellt den Benutzern Informationen in einer einzigen Benutzeroberfläche zur Verfügung
  - Hinzufügen von Registerkarten, Connectors und Bots
  - Live Chat, Audio/Videokonferenzen, aufgezeichnete Besprechungen

- Yammer: Verbindung über die Organisation ( Unternehmenssoziales) – äußere Schleife
  - Communities of Practice – funktionsübergreifende Gruppen von Personen, die ein gemeinsames Interesse oder Fachwissen teilen, aber nicht unbedingt täglich zusammenarbeiten
  - Verbindung mit dem Führungsteam, Lerngemeinschaften, rollenbasierte Gemeinschaften

- Outlook-Gruppen: moderne DL (e-Mail-basierte Zusammenarbeit)
  - Allgegenwärtig für gezielte Kommunikation
  - Upgrade von Verteilerlisten auf Microsoft 365-Gruppen – [Warum sollten Sie ein Upgrade](https://support.microsoft.com/office/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188) durchführen?

- SharePoint – zentrale Inhalte für die Zusammenarbeit für alle Microsoft 365-Gruppen
  - Jede Gruppe Ruft eine verbundene SharePoint-Teamwebsite ab.
  - Freigeben von Inhalten, Erstellen benutzerdefinierter Seiten und Verfassen von Nachrichten
  - [Verbinden](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview) vorhandener SharePoint-Teamwebsites mit neuen Microsoft 365-Gruppen

##  <a name="managing-and-governing-microsoft-365-at-scale"></a>Verwalten und Steuern von Microsoft 365 bei der Skalierung

Microsoft 365 Groups verfügt über eine Vielzahl von Tools zur Implementierung von Steuerungsfunktionen, die Ihre Organisation möglicherweise benötigt. Der folgende Abschnitt beschreibt die Möglichkeiten, empfiehlt bewährte Methoden und gibt Hinweise, wie die richtigen Fragen gestellt werden können, um die Anforderungen an die Governance zu bestimmen und wie diese erfüllt werden können.

**In diesem Abschnitt**:
- [Steuern der Benutzer, die Microsoft 365-Gruppen erstellen können](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#control-who-can-create-office-365-groups)
- [Vorläufiges Löschen und Wiederherstellen der Gruppe](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-soft-delete-and-restore)
- [Gruppenbenennungsrichtlinie](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-naming-policy)
- [Gruppenablaufrichtlinie](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-expiration-policy)
- [Gruppengastzugriff](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-guest-access)
- [Gruppenrichtlinien und Informationsschutz](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-policies--information-protection)
- [Upgrade herkömmlicher Tools für die Zusammenarbeit](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#upgrade-traditional-collaboration-tools)
- [Gruppenberichterstellung](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#groups-reporting)

### <a name="control-who-can-create-microsoft-365-groups"></a><a name="control-who-can-create-office-365-groups"></a>Steuern der Benutzer, die Microsoft 365-Gruppen erstellen können
Gruppen können von Endbenutzern aus mehreren Endpunkten einschließlich Outlook, SharePoint, Teams und anderen Umgebungen erstellt werden.

![Bildbeschreibung](../../media/04.png)
> [!Tip]
>- Ziehen Sie die Selbstbedienung stark in Betracht, um Gruppenbesitzer zu befähigen.
>- Dokumentieren und teilen Sie mit, wie eine Gruppe angefordert wird.
>- Überprüfen Sie noch einmal, wer während Ihrer Cloud Journey Gruppen erstellen kann.
>- Verwenden Sie die dynamische Mitgliedschaft, um die Mitglieder der Sicherheitsgruppe zum Steuern der Gruppenerstellung zu konfigurieren.
>- Bewerten Sie, welche Gruppen Szenarien über eine dynamische Mitgliedschaft verwaltet werden können, und lassen Sie Self-Service für den Rest zu.

Es gibt drei primäre Modelle für die Einrichtung in Gruppen: Open, IT-LED und Controlled. In der folgenden Tabelle werden die Vorteile des jeweiligen Modells beschrieben.

| Modell          | Vorteile                                                   |
| -------------- | ------------------------------------------------------------ |
| Offen (Standard) | Benutzer können bei Bedarf ihre eigenen Gruppen erstellen, ohne auf einen IT-Mitarbeiter warten oder einen IT-Mitarbeiter um Hilfe bitten zu müssen. |
| IT-gesteuert         | Benutzer fordern eine Gruppe von der IT an. Die IT kann die Benutzer bei der Auswahl der für ihre Anforderungen am besten geeigneten Tools für die Zusammenarbeit unterstützen. |
| Kontrolliert     | Die Gruppenerstellung ist auf bestimmte Personen, Teams oder Dienste beschränkt. Weitere Informationen finden Sie unter [Manage who can create Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups). |

Ihre Organisation könnte spezifische Anforderungen haben, um strenge Kontrollen darüber einzuführen, wer Gruppen erstellen kann. Verwenden Sie die folgende Tabelle, um die Entscheidung zu erleichtern, welches Bereitstellungsmodell für Ihre Organisation geeignet ist.

|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Welches Bereitstellungsmodell passt zu den Anforderungen Ihrer Organisation?</li><li>Ist für Ihre Organisation die Beschränkung der Gruppenerstellung auf Administratoren erforderlich?</li><li>Ist für Ihre Organisation die Beschränkung der Gruppenerstellung auf Sicherheitsgruppenmitglieder erforderlich?</li><li>Ist für Ihre Organisation, dass einige Gruppen dynamisch auf der Grundlage von Benutzerattributen, wie z. B. Abteilung, erstellt werden erforderlich?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für die Erstellung von Gruppen und Teams.</li><li>Planen Sie, diese Anforderungen als Teil Ihres Gruppen-Rollouts zu implementieren.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um Benutzer über das erwartete Verhalten zu informieren</li><li>Planen Sie ggf. die Einführung einer dynamischen Mitgliedschaft.</li></ul>|

> [!Important]
> Das Einschränken der Gruppen-und TEAMERSTELLUNG kann die Produktivität der Benutzer verlangsamen, da viele Microsoft 365-Dienste die Erstellung von Gruppen für den Dienst erfordern. Weitere Informationen finden Sie unter [Gründe für die Erstellung von Microsoft 365-Gruppen durch Steuerelemente.](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide%23why-control-who-creates-office-365-groups)

#### <a name="resources"></a>*Ressourcen*
- [Verwalten von Personen, die Microsoft 365-Gruppen erstellen können](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide)
- [Dynamisches Auffüllen von Gruppen anhand von Objektattributen](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-with-advanced-rules)
- [Vorgehensweise ändern der Standardeinstellung von Microsoft 365-Gruppen für Outlook in "öffentlich" oder "Privat"](https://support.office.com/article/office-365-groups-in-outlook-private-by-default-36236e39-26d3-420b-b0ac-8072d2d2bedc)
- [Synchronisieren von Sicherheitsgruppen mit der Teammitgliedschaft ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Syncing-Security-Groups-with-team-membership/ba-p/241959)

### <a name="group-soft-delete-and-restore"></a><a name="group-soft-delete-and-restore"></a>Vorläufiges Löschen und Wiederherstellen der Gruppe
Wenn Sie eine Microsoft 365-Gruppe gelöscht haben, wird Sie standardmäßig 30 Tage lang aufbewahrt. Dieser 30-Tage-Zeitraum wird als "vorläufiges Löschen" bezeichnet, weil Sie die Gruppe immer noch wiederherstellen können. Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.

> [!Tip]
>- Teilen Sie den Wiederherstellungsvorgang Ihren Benutzern mit.
>- Schulen Sie Ihr Helpdesk-Team.
>- Verfolgen Sie bevorstehende Gruppen, die mit Hilfe des PowerShell-Skripts gelöscht werden sollen.

|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Möchten Sie, dass bestimmte Objekte für den langfristigen Speicher aufbewahrt werden?</li><li>Gibt es bestimmte Aufbewahrungsanforderungen für Ihre Organisation?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Kommunizieren und veröffentlichen Sie Ihre Lösch- und Wiederherstellungsrichtlinien, um Benutzer über das erwartete Verhalten zu informieren </li><li> Dokumentieren Sie die Anforderungen Ihrer Organisation an die Überwachung gelöschter Gruppen.</li><li>Planen Sie, diese Anforderungen als Teil Ihres Gruppen-Rollouts zu implementieren.</li></ul>|

> [!Important]
>Wenn ein Benutzer während des Vorgangs "Vorläufiges Löschen" versucht, auf die Website zuzugreifen, wird eine "403 Verboten"-Meldung angezeigt. Wenn der Benutzer nach Ablauf dieses Zeitraums versucht, auf die Website zuzugreifen, wird eine "404 Nicht gefunden"-Meldung angezeigt.

#### <a name="resources"></a>*Ressourcen*
- [Wiederherstellen einer gelöschten Microsoft 365-Gruppe](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group?ui=en-US&rs=en-001&ad=US)
- [Wiederherstellen einer gelöschten Microsoft 365-Gruppe in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)
- [Löschen von Gruppen mit dem Cmdlet "Remove-UnifiedGroup"](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)

### <a name="group-naming-policy"></a><a name="group-naming-policy"></a>Gruppenbenennungsrichtlinie
Eine Benennungsrichtlinie kann Ihnen und Ihren Benutzern bei der Identifizierung der Funktion der Gruppe, der Mitgliedschaft, der geografischen Region oder der Person helfen, die die Gruppe erstellt hat. Die Benennungsrichtlinie kann auch hilfreich beim Kategorisieren von Gruppen im Adressbuch sein. Mithilfe der Richtlinie können Sie bestimmte Wörter in Gruppennamen und -aliasen blockieren.

> [!Tip]
> - Verwenden Sie kurze Zeichenfolgen als Namenszusatz.
> - Verwenden Sie Attribute mit Werten.
> - Lassen Sie sich nicht zu kreativ sein, die gesamte Name-Länge hat maximal 264 Zeichen.
> - Laden Sie spezifische blockierte Wörter Ihrer Organisation hoch, um die Nutzung einzuschränken.


|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Ist für Ihre Organisation eine bestimmte Benennungskonvention für Gruppen erforderlich?</li><li>Ist für Ihre Organisation die Benennungskonvention für alle Workloads erforderlich?</li><li>Gibt es in Ihrer Organisation bestimmte Wörter, die Sie den Benutzern verbieten wollen?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für Benennungs Gruppen. </li><li> Planen Sie, diese Anforderungen als Teil Ihres Gruppen-Rollouts zu implementieren.</li><li> Kommunizieren und veröffentlichen Sie die Benennungsrichtlinien und -Standards, um die Benutzer zu informieren.</li></ul>|

> [!Important]
>Die Benennungsrichtlinie wird übergreifend auf Gruppen angewendet, die in allen Workloads (wie Outlook, Microsoft Teams, SharePoint, Planner, Yammer usw.) erstellt werden. Sie wird sowohl auf den Gruppennamen als auch auf den Gruppenalias angewendet. Außerdem wird sie angewendet, wenn ein Benutzer eine Gruppe erstellt und wenn ein Gruppenname oder -alias bei einer bestehenden Gruppe bearbeitet wird.

#### <a name="resources"></a>*Ressourcen*
- [Microsoft 365 gruppenbenennungsrichtlinie](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)
- [Erzwingen einer Benennungsrichtlinie für Microsoft 365-Gruppen in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)
- [Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen](https://go.microsoft.com/fwlink/?linkid=868341)
- [Vorschaufeatures für die Gruppenbenennung](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/NamingPolicy)

### <a name="group-expiration-policy"></a><a name="group-expiration-policy"></a>Gruppenablaufrichtlinie
Administratoren können einen Ablaufzeitraum angeben, und jede Gruppe, die das Ende dieses Zeitraums erreicht und nicht verlängert wird, wird gelöscht. Der Ablaufzeitraum beginnt beim Erstellen der Gruppe oder am Datum der letzten Verlängerung. Gruppenbesitzer erhalten vor dem Ablauf automatisch eine E-Mail, die es ihnen erlaubt, die Gruppe für ein weiteres Ablaufintervall zu erneuern. Aktive Gruppen verlängern sich automatisch.

Das Festlegen eines Ablaufs für eine Gruppe bewirkt Folgendes:
- Besitzer der Gruppe werden vor Erreichen des Ablaufs aufgefordert, die Gruppe zu erneuern.
- Nicht erneuerte Gruppen werden gelöscht.
- Gelöschte Gruppen können innerhalb von 30 Tagen von den Gruppenbesitzern oder vom Administrator wiederhergestellt werden

> [!Tip]
> - Pilotprojekt zunächst mit bestimmten Gruppen.
> - Wählen Sie inaktive Gruppen basierend auf dem Aktivitätsbericht im Microsoft 365 Admin Center aus.
> - Informieren Sie Gruppenbesitzer über den Verlängerungsprozess.
> - Binden Sie Ihr Helpdesk-Team ein.
> - Stellen Sie sicher, dass Gruppen mehrere Besitzer haben und konfigurieren Sie E-Mails für verwaiste Gruppen.


|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Muss in Ihrer Organisation ein Ablaufdatum für Teams angegeben werden?</li><li>Bestimmen Sie die Strategie für den Umgang mit verwaisten Gruppen.</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation an Gruppen Ablauf, Datenaufbewahrung und Archivierung.</li><li>Planen Sie, diese Anforderungen als Teil Ihres Gruppen-Rollouts zu implementieren.</li><li>Planen Sie die Implementierung einer benutzerdefinierten Arbeit, um über Gruppen zu berichten, die über nur einen einzigen oder keinen Besitzer verfügen. </li></ul>|

> [!Important]
>Wenn Sie die Ablaufrichtlinie ändern, berechnet der Dienst das Ablaufdatum für jede Gruppe neu. Er beginnt immer ab dem Datum, an dem die Gruppe erstellt wurde, und wendet dann die neue Ablaufrichtlinie an.

#### <a name="resources"></a>*Ressourcen*
- [Ablaufrichtlinie für Microsoft 365-Gruppen](https://support.office.com/article/Office-365-Group-Expiration-Policy-8d253fe5-0e09-4b3c-8b5e-f48def064733?ui=en-US&rs=en-US&ad=US)
- [Konfigurieren der Ablaufrichtlinie für Microsoft 365-Gruppen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

### <a name="group-guest-access"></a><a name="group-guest-access"></a>Gruppengastzugriff
Administratoren können steuern, ob Gastzugriff auf Microsoft 365-Gruppen für Ihre gesamte Organisation oder für einzelne Microsoft 365-Gruppen zugelassen werden soll. Sie können auch steuern, wer Gästen ermöglichen kann, zu Gruppen hinzugefügt zu werden.
>[!Tip]
>- Aktivieren des Gastzugriffs auf Mandantenebene. Bei Bedarf, für bestimmte Gruppen blockieren.
>- Verwalten mit Erlauben/Sperren von Gastdomänen, Rolle „Gasteinladender“, Zugangsprüfungen, Nutzungsbedingungen.
>- Nachverfolgen von Gastbenutzeraktivitäten mithilfe von Überwachungsprotokollen.

|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Müssen Sie die Möglichkeit, Gäste zu Teams auf Gruppenbasis hinzuzufügen, einschränken?</li><li> Ist für Ihre Organisation die Vorlage relevanter Haftungsausschlüssen für rechtliche oder Compliance-Anforderungen erforderlich?</li><li>Gibt es in Ihrer Organisation die Notwendigkeit, den Verwaltungsaufwand für das Hinzufügen und Entfernen von Benutzern zu reduzieren?</li><li>Wird in Ihrer Organisation die Kontrolle des Gast-/externen Zugriffs erwartet?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen an den Gast-/externen Zugriff für bestimmte klassifizierte Gruppen, einschließlich der Aufbewahrungszeit und des Auftretens.</li><li>Anforderungen an die Dokument Organisation, für welche Gruppen Nutzungsbedingungen und Zugriffsüberprüfung erforderlich sind. </li><li>Führen Sie Überprüfungen durch, um Gruppenmitgliedschaften sowohl für interne als auch für Gastbenutzer effizient zu verwalten.</li></ul>|


#### <a name="resources"></a>*Ressourcen*
- [Zusammenarbeit mit Personen außerhalb Ihrer Organisation](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)
- [Verwalten des Gastzugriffs in Microsoft 365-Gruppen](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups)
- [Gastzugriff in Microsoft 365-Gruppen](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)
- [Zugriffsüberprüfungen in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
- [Nutzungsbedingungsfeature für Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-tou)
- [Verbund mit Google](https://docs.microsoft.com/azure/active-directory/b2b/google-federation)

### <a name="group-policies--information-protection"></a><a name="group-policies--information-protection"></a>Gruppenrichtlinien und Informationsschutz
Microsoft 365-Gruppen basieren auf den erweiterten Sicherheits-und Compliance-Funktionen von Microsoft 365 und unterstützen Klassifizierungen, Überwachung und Berichterstellung, Compliance-Inhaltssuche, e-Discovery, Aufbewahrungspflicht und Aufbewahrungsrichtlinien.
>[!Tip]
>- Konfigurieren Sie Klassifizierungen, Verwendungsrichtlinien und Bezeichnungen, die auf die Bedürfnisse Ihrer Organisation abgestimmt sind.
>- Aufbewahrungsrichtlinien können unabhängig von Bezeichnungen definiert werden.
>- Aktivitäten von Überwachungsgruppen: Erstellen, Löschen usw.
>- Verwalten des Datenschutzes und des Gastzugriffs basierend auf der Klassifizierung.

|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Hat Ihre Organisation bestimmte Verwendungsanforderungen, die allen Benutzern mitgeteilt werden müssen?</li><li>Ist für Ihre Organisation die Klassifizierung aller Inhalte erforderlich?</li><li>Ist für Ihre Organisation die Aufbewahrung von Inhalten für einen bestimmten Zeitraum erforderlich?</li><li>Müssen in Ihrer Organisation bestimmte Datenaufbewahrungsrichtlinien auf Gruppen angewendet werden?</li><li>Wird in Ihrer Organisation die Fähigkeit zur Archivierung inaktiver Gruppen gefordert, um den Inhalt zu erhalten?</li><li>Müssen Ersteller von Gruppen in der Lage sein, organisationsspezifische Klassifizierungen für Teams zuzuweisen?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Dokumentieren der Nutzungsrichtlinien Ihrer Organisation für Gruppen</li><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für die Klassifizierung.</li><li>Bestimmen Sie die Richtlinien, die auf der Grundlage der Klassifizierung durchgesetzt werden sollen, beispielsweise Sensitivität, Aufbewahrung, Gastzugriff.</li><li>Definieren Sie die Vertraulichkeitsbezeichnungen für Ihre Organisation und welche Schutzeinstellungen Sie damit verbinden möchten.</li><li>Definieren Sie eine Bezeichnungsrichtlinie, um zu kontrollieren, welche Benutzer und Gruppen diese Bezeichnungen sehen.</li><li>Konfigurieren Sie die [Vorschau der Gruppenvertraulichkeitsbezeichnung](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) und beginnen Sie, die Gruppen in Ihrer Organisation zu klassifizieren.</li><li>Planen Sie, diese Anforderungen als Teil Ihres Gruppen-Rollouts zu implementieren.</li></ul>|


#### <a name="resources"></a>*Ressourcen*
- [Link zu Ihren Microsoft 365-Gruppen-Nutzungsrichtlinien](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [Erstellen von Klassifizierungen für Office-Gruppen in Ihrer Organisation](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- [Konfigurieren der Gruppeneinstellungen](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)
- [Übersicht über Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [Übersicht über Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)
- [Übersicht über Bezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/labels)
- [Durchsuchen des Überwachungsprotokolls](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
- [Erstellen oder Entfernen eines Compliance-Archivs](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)
- [Erstellen einer Erhaltungsrichtlinie](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [Ausführen einer Inhaltssuche im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/content-search)
- [Massenerstellen und Veröffentlichen von Aufbewahrungsbeschriftungen mithilfe von PowerShell](https://docs.microsoft.com/microsoft-365/compliance/bulk-create-publish-labels-using-powershell)

### <a name="upgrade-traditional-collaboration-tools"></a><a name="upgrade-traditional-collaboration-tools"></a>Upgrade herkömmlicher Tools für die Zusammenarbeit
Jahrelang haben Organisationen mit Verteilergruppen gearbeitet, um mit Personengruppen innerhalb und außerhalb des Unternehmens zu kommunizieren und zusammenzuarbeiten. Nun bieten Microsoft 365-Gruppen in Outlook jedoch eine leistungsstärkere Lösung für die Zusammenarbeit. Darüber hinaus ist es wichtig, dass Sie eine Verbindung mit einer Microsoft 365-Gruppe mit einer vorhandenen SharePoint-Website herstellen können, wenn Sie diese Website modernisieren möchten.

>[!Tip]
>- Aktualisieren Sie alle berechtigten Verteilerlisten in Sekundenschnelle über das Exchange Admin Center oder mithilfe von PowerShell-Cmdlets.
>- Verbinden vorhandener SharePoint-Teamwebsites mit neuen Microsoft 365-Gruppen

|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Verfügt Ihre Organisation über Verteilerlisten, die [nicht berechtigt](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists#how-do-i-check-which-dls-are-eligible-for-upgrade) sind, ein Upgrade durchzuführen?<li>Bestimmen Sie, zu welcher Art von Gruppe die am besten migrierte Verteilerliste gehört.</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Ermitteln Sie, welche Verteilerlisten Kandidaten für ein Upgrade auf Microsoft 365-Gruppen sind.</li><li>Analysieren Sie Ihre vorhandenen SharePoint-Teamwebsites, um zu sehen, welche Websites für eine Gruppenverbindung bereit sind.</li><li>Lassen Sie andere Teams in Ihrem Unternehmen wissen, dass Sie Ihre Verteilerliste aktualisiert haben und welche Schritte Sie für eine erfolgreiche Umstellung unternommen haben!</li></ul>|


#### <a name="resources"></a>*Ressourcen*
- [Aktualisieren von Verteilerlisten (DL) auf Gruppen in Outlook](https://aka.ms/whyupgradedls)
- Upgrade mit nur einem Klick über das Exchange Admin Center oder über [PowerShell-Skripts](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)
- [Migrieren von Verteilerlisten zu Microsoft 365-Gruppen – Administratorhilfe](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)
- [Verbinden vorhandener SharePoint-Websites mit Microsoft 365-Gruppen:](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group)
- [Analysieren und Verwenden der Scannerdaten](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group-scanner)
- [SharePoint-Modernisierungsscanner](https://github.com/SharePoint/sp-dev-modernization/tree/master/Tools/SharePoint.Modernization) (ein Tool, das auf GitHub gespeichert ist)

### <a name="groups-reporting"></a><a name="groups-reporting"></a>Gruppenberichterstellung
Im Microsoft 365 Reports-Dashboard wird die Aktivitätsübersicht für die Microsoft-Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten.
> [!TIP]
>- Sie können die Gruppenberichte verwenden, um Einblicke in die Aktivitäten von Microsoft 365-Gruppen in Ihrer Organisation zu erhalten und zu sehen, wie viele Gruppen erstellt und verwendet werden.
>-Der Microsoft 365-Gruppenbericht kann für Trends in den letzten 7 Tagen, 30 Tagen, 90 Tagen oder 180 Tagen angezeigt werden.
>- Überwachen Sie die Gruppenaktivitäten in den Unterhaltungen der Gruppenpostfächer, die Aktivitäten der Gruppenstandorte/Dateien, Details zur Gruppenmitgliedschaft einschließlich der Anzahl externer Mitglieder.
>- Überwachen Sie regelmäßig, um die Gruppenbesitzer aktiver Gruppen zu erreichen, um Anwendungsfälle zu lernen und sie intern zu erweitern.
>- Nutzen Sie Power BI-Inhaltspakete, um weitere Einblicke zu erhalten.


|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Erfordert Ihre Organisation regelmäßige Berichte, um die Verwendung von Microsoft 365-Gruppen zu verstehen?<li>Ist für Ihre Organisation eine Berichterstattung über alle Gruppen mit externen Mitgliedern erforderlich?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für regelmäßige Überprüfung von Aktivitätsberichten für Gruppen.</li></ul>|


#### <a name="resources"></a>*Ressourcen*
- [Microsoft 365-Berichte im Admin Center](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)
- [Inhaltspaket zur Office 365-Einführung](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics)
- [Azure AD-Inhaltspaket](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-power-bi-content-pack-how-to)
- [Microsoft Graph-Gruppenaktivitäts-API](https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/office_365_groups_activity_reports)
- [Microsoft 365 Groups-Bericht (Unified Groups)](https://gallery.technet.microsoft.com/office/Office-365-Groups-Report-7e3e161b)
- [Überwachungsaktivitätsberichte im Azure Active Directory-Portal](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-audit-logs)
- [Microsoft Graph – Verwenden einer Delta-Abfrage zum Nachverfolgen von Änderungen](https://docs.microsoft.com/graph/delta-query-overview)

## <a name="getting-started-based-on-your-cloud-adoption-journey"></a>Erste Schritte auf der Grundlage Ihrer Einführung der Cloud Journey

Microsoft 365-Gruppen bieten eine umfassende Palette von Steuerungsfunktionen, die Ihre Organisation möglicherweise benötigt. Betrachten Sie die folgenden Organisationsprofile als Orientierungshilfe, um die bewährten Methoden zu verstehen, die richtigen Fragen zu stellen, um die Anforderungen an die Unternehmensführung zu bestimmen, und um herauszufinden, wie diese erfüllt werden können.

**Betrachten Sie die folgenden Organisationsprofile:**
- Kleinunternehmen
- Mittlere Unternehmen
- Reguliert oder Unternehmen

### <a name="small-business"></a>Kleinunternehmen
Stellen Sie sich eine Organisation vor, die Microsoft 365 mit mindestens Exchange Online-und SharePoint Online-Lizenzen bereitgestellt hat, die die Business Essentials-und Business Premium-Pläne enthält, und die Pläne Enterprise E1, E3 und E5 ohne Azure Active Director Premium Licensing.

| Stufe 1 | Beschreibung |
| --------------- | ------------------------------------------------------------ |
| Richtlinien |<ul><li>Stellen Sie sich ein Self-Service-proprovisioning-Modell vor.</li><li> Gruppen in Outlook- und SharePoint-Websites sind [standardmäßig privat](https://techcommunity.microsoft.com/t5/Office-365-Groups/Groups-in-Outlook-and-Group-connected-team-sites-are-now-private/m-p/186395).</li><li> Gruppen können erstellt werden, indem bestehende Verteilerlisten (DLs) entweder einzeln oder in großen Mengen über PowerShell upgraden werden. Weitere Informationen finden Sie unter [Upgrade Verteilerlisten to Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists).</li><li> Aktivieren Sie den Gastzugriff, aber regeln Sie mit Erlauben/Sperren von Gastdomänen.</li><li> Verwenden Sie Gruppenberichte, um Einblicke zu gewinnen, wie Benutzer Gruppen verwenden.</li><li> Erstellen Sie ein organisationsweites Team Microsoft Teams-Team als Möglichkeit für alle, Teil eines einzelnen Teams für die Zusammenarbeit zu sein. </li></ul>|
| Nächste Schritte      |<ul><li>Erwägen Sie die Verwendung von [Website-Designs und Website-Skripts](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview) zum Definieren des Standardentwurfs für Steuerelemente mithilfe der Aktionen, die in der [JSON-Schemareferenz](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema) definiert sind.</li><li>Überprüfen von [Gruppen Berichten](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups).</li><li>Nachverfolgen von Gesamt Gruppen und inaktiven/aktiven Gruppen.</li><li>Nachverfolgen von Exchange-und SharePoint-Speicher verwendet.</li><li>Zeigen Sie Gruppenaktivitäten über die Unterhaltungen der Gruppenpostfächer, die Aktivität der Gruppenstandorte/Dateien usw. an.</li></ul> |

### <a name="medium-sized-business"></a>Mittlere Unternehmen
Zusätzlich zu den obigen Empfehlungen sollten Sie Folgendes für mittelständische Unternehmen betrachten, die Microsoft 365 mit mindestens einer Enterprise E3/E5 mit Azure Active Directory Premium P1-Lizenzen bereitgestellt haben.

| Stufe 1 | Beschreibung |
| --------------- | ------------------------------------------------------------ |
| Richtlinien |<ul><li>Entscheiden Sie sich für ein offenes oder IT-gesteuertes Bereitstellungsmodell.</li><li> Erwägen Sie die Schaffung bestimmter Gruppen, die an [dynamische Mitgliedschaftsregeln](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) auf der Grundlage von Azure AD-Attributen wie Abteilung gebunden sind</li><li> Definieren Sie Klassifizierungen innerhalb Ihrer Organisation, z. B. „Hochvertraulich“, „Vertraulich (Standard)“, „Allgemein“.</li><li>  Definieren Sie die Richtlinien auf der Grundlage von Klassifizierungen wie Aufbewahrung und Vertraulichkeit.</li><li> SharePoint ist der inhaltsdienst für jede Microsoft 365-Gruppe. Erwägen Sie den Entwurf und die [Bereitstellung von SharePoint Online-Websites für drei Schutzebenen](https://docs.microsoft.com/office365/enterprise/deploy-sharepoint-online-sites-for-three-tiers-of-protection) (Basisplan, vertraulich und hochvertraulich). Weitere Informationen zu diesen drei Schutzebenen finden Sie unter [Sichern von SharePoint Online-Websites und -Dateien](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files).</li><li> Öffentliche und private Gruppen werden standardmäßig in der globalen Adressliste (GAL) aufgelistet. Bestimmen Sie, welche Gruppen in der globalen Adressliste erscheinen sollen, insbesondere Gruppen, die außerhalb von Microsoft Teams erstellt wurden.  Verwenden Sie die Cmdlets "HiddenFromAddressListsEnabled" oder "HidefromExchangeClients" des Cmdlets "Group [-Unifiedgroup](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx) ", um bestimmte Gruppen auszublenden.</li></ul> |
| Nächste Schritte      |<ul><li>Bestimmen von [Nutzungsrichtlinien](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets), um die Benutzer über die bewährten Methoden zu informieren, die dazu beitragen, die Effektivität der Gruppe zu gewährleisten und interne Inhaltsrichtlinien zu kommunizieren. Beispiel: Grundlegendes zu Klassifizierungen, Richtlinien und Verfahren. </li><li>Bestimmen Sie den Zeitraum des Gruppenlebenszyklus, in dem Gruppen erneuert werden müssen oder gelöscht werden sollen – Ablaufrichtlinie.</li><li>Erwägen Sie die Erstellung der folgenden benutzerdefinierten Aufträge, um Richtlinien basierend auf Klassifizierungen zu implementieren.</li><li>Legen Sie den Datenschutz auf "Privat" fest.</li><li>Externe Mitgliedschaft/Freigabe deaktivieren. </li><li>E-Mail-Nachrichten zur Benachrichtigung von Gruppenmitgliedern für Gruppen [ohne Besitzer](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</li><li>Erzwingen der Besitzrichtlinie (mind. 2 Besitzer)</li><li> Definieren von Aufbewahrungsrichtlinien für Gruppen auf der Grundlage der Klassifizierung. </li><li>Übersicht über Aufbewahrungsrichtlinien.</li><li>Verwenden von PowerShell zum Identifizieren von Gruppen mit einer Klassifizierung und [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy?view=exchange-ps).</li><li>Erwägen Sie die Verwendung von Website-Designs und Website-Skripts zum Definieren der Steuerelemente mithilfe der Aktionen, die in der [JSON-Schemareferenz](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema) definiert sind.</li><li>Erwägen Sie [ein einfaches Websiteverzeichnis mit einem Websitedesign](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-trigger-flow-tutorial) und Microsoft Flow zu erstellen. Wenn Sie eine Website mit diesem Websitedesign erstellen, werden Details zu der Website erfasst und in eine Liste geschrieben. </li></ul>|

### <a name="regulated-or-enterprise"></a>Reguliert oder Unternehmen
Zusätzlich zu den obigen Empfehlungen sollten Sie Folgendes für hochregulierte oder große Enter Prises wie Government, Financial Services oder Healthcare verwenden, die Office 365 mit mindestens einer Enterprise E3/E5 mit Azure Active Directory Premium P1/P2-Lizenzen bereitgestellt haben.

| Stufe 1 | Beschreibung |
| --------------- | ------------------------------------------------------------ |
| Richtlinien |<ul><li> Definieren von Richtlinien für die Daten-Governance der SharePoint-Website, die der Gruppe basierend auf der Klassifizierung zugeordnet ist.</li><li>[Schützen Sie SharePoint Online Dateien mit Beschriftungen und DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</li><li>[Schützen von SharePoint Online-Dateien mit Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</li><li> Gruppen Website, die in einer Region mit dem bevorzugten Datenspeicherort des Benutzers ([Multi-Geo](https://docs.microsoft.com/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365)) verbunden ist.</li><li> Mitgliedschaftsüberprüfungen für Gruppen mit externen Mitgliedern ([Zugriffsüberprüfungen](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-access-reviews-overview)).</li><li>Sicherstellen, dass Mitarbeiter oder Gastbenutzer relevante Haftungsausschlüsse angezeigt werden, um rechtliche oder compliancebezogene Anforderungen zu erfüllen. ([Nutzungsbedingungen](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou)).</li><li>Identifizieren und melden Sie Microsoft 365-Gruppen mit einer bestimmten [Klassifizierung, die auch externe Benutzer haben](https://techcommunity.microsoft.com/t5/Office-365-Groups/Sample-Powershell-to-identify-groups-with-HBI-classification-and/m-p/215561).</li><li>Geheime Gruppen, in denen Mitgliedschaften versteckt werden mussten, müssen bei der Gruppenerstellung mit dem Cmdlet [New-UnifiedGroup](https://technet.microsoft.com/library/mt219359(v=exchg.160).aspx) (mit dem Schalter "HiddenGroup-MembershipEnabled") erstellt werden.</li><li>Definieren Sie die [Vertraulichkeits Bezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) für die Organisation, um den [Zugriff auf Inhalte zu beschränken, indem Sie Verschlüsselung verwenden](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) und in bestimmten Microsoft 365-Gruppen veröffentlichen.</li><li>Verhindern, dass vertrauliche Inhalte Ihre Organisation auf Geräten mit Windows verlassen, indem Sie [Vertraulichkeitsbezeichnungen mit Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553) verwenden. |
| Nächste Schritte      | <ul><li> Verwenden Sie Website-Design und Website-Skripts, um die Standard-[Aktionen](https://developer.microsoft.com/office/blogs/site-scripts-site-designs-summer-2018-update/) zu definieren, die beim Erstellen einer neuen Website auftreten. [Konfigurieren Sie beispielsweise die Einstellung für die externe Freigabe](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-apply-external-sharing-setting) oder [lösen Sie einen Microsoft Flow aus, um eine Azure-Funktion aufzurufen](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-azure-function) und Konfigurationen anzuwenden, die nicht nativ unterstützt werden. </li><li> Dokumentanforderungen zum [Schutz SharePoint Online Dateien mit Bezeichnungen und DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) auf Websites, die Microsoft 365-Gruppen zugeordnet sind.</li><li>Dokumentieren Sie die Organisationsanforderungen, um [SharePoint Online Websites und Dateien zu sichern](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-sharepoint-online-sites-and-files) , die mit Microsoft 365-Gruppen verbunden sind. </li><li>Dokumentieren Sie die Anforderungen der Organisation zur Veröffentlichung von [Vertraulichkeitsbezeichnungen](hhttps://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) für bestimmte Benutzer oder Gruppen, um den Inhalt zu schützen.</li></ul> |

## <a name="groups-management-capability-planning-checklist"></a>Planungscheckliste der Verwaltungsfunktion von Gruppen

Eine Reihe von gruppenbezogenen Steuerelementen kann über Azure Active Directory verwaltet werden. Weitere Informationen zum Erstellen von Gruppeneinstellungen finden Sie unter [Azure Active Directory-Cmdlets zum Konfigurieren von Gruppeneinstellungen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).

Verwenden Sie die folgende Tabelle, um festzustellen, welche Funktionen Sie für die Bereitstellung der Anforderungen Ihrer Organisation benötigen. Es wird Ihnen helfen, die benötigten Lizenzen zu ermitteln, damit Sie vorausplanen können.

| **Funktion**      | **Details**                                    | **Azure AD Premium-Lizenz erforderlich** | **Entscheidung** |
| ------------------- | ---------------------------------------------- | ------------------------------------- | ------------ |
| Gruppenbenennungsrichtlinie | Verwenden Sie Präfix-Suffix-basierte, benutzerdefinierte blockierte Wörter. | P1                                    |      Noch nicht festgelegt     |
| Gruppenklassifizierung | Zuweisen von Klassifizierungen zu Teams. | P1                                    |   Noch nicht festgelegt        |
| Gruppengastzugriff | Zulassen oder verhindern Sie das Hinzufügen von Gästen zu Gruppen. | Nein                                    |  Noch nicht festgelegt        |
| Gruppenerstellung | Begrenzen der Teamerstellung auf Administratoren. | Nein                                    |   Noch nicht festgelegt        |
| Gruppenerstellung | Begrenzen der Teamerstellung auf Sicherheitsgruppenmitglieder. | P1                                    |     Noch nicht festgelegt      |
| Richtlinien für die Gruppennutzung | Festlegen eines Links zu den Richtlinien für die Gruppennutzung, der an allen Endpunkten der Gruppenerstellung sichtbar sein wird. | P1                                    |   Noch nicht festgelegt        |
| Ausgeblendete Mitgliedschaft | Ausblenden der Mitglieder der Microsoft 365-Gruppe für Benutzer, die nicht Mitglied der Gruppe sind | Nein                                    |   Noch nicht festgelegt        |
| Ablaufrichtlinie | Verwalten Sie den Lebenszyklus von Microsoft 365-Gruppen, indem Sie eine Ablaufrichtlinie festlegen. | P1                                    |  Noch nicht festgelegt        |
| Gruppenaktivitätsberichten | Erhalten Sie Einblicke in die Aktivitäten von Microsoft 365-Gruppen in Ihrer Organisation, und sehen Sie, wie viele Microsoft 365-Gruppen erstellt und verwendet werden. | Nein                                    |    Noch nicht festgelegt       |
| Aufbewahrungsrichtlinie | Speichern oder löschen Sie Daten für einen bestimmten Zeitraum, indem Sie Aufbewahrungsrichtlinien für Microsoft 365-Gruppen im Security & Compliance Center festlegen. **Hinweis:** Für die Nutzung dieser Funktion ist die Lizenzierung von Office 365 Enterprise E3 oder höher erforderlich. | Nein                                    |    Noch nicht festgelegt       |
| Richtlinie zur Verhinderung von Datenverlust | Identifizieren vertraulicher Informationen auf verbundenen Websites der Microsoft 365-Gruppe und verhindern der versehentlichen Freigabe. **Hinweis:** Für die Nutzung dieser Funktion ist die Lizenzierung von Office 365 Enterprise E3 oder höher erforderlich. | Nein                                    |     Noch nicht festgelegt      |
| Archivieren und Wiederherstellen | Archivieren Sie ein Team, wenn es nicht mehr aktiv ist, Sie möchten es jedoch zu Referenzzwecken beibehalten oder in Zukunft erneut aktivieren. | Nein                                    |   Noch nicht festgelegt        |
| Zugriffsüberprüfungen | Durchführen von Überprüfungen zum effizienten Verwalten von Gruppenmitgliedschaften sowohl für interne als auch für Gastbenutzer | P2                                    |   Noch nicht festgelegt       |
| Nutzungsbedingungen | Eine einfache Methode damit Organisationen komfortabel Informationen für Endbenutzer anzeigen können. Dadurch wird sichergestellt, dass Benutzern relevante Haftungsausschlüsse angezeigt werden, um rechtliche oder compliancebezogene Anforderungen zu erfüllen. | P1                                    |         Noch nicht festgelegt  |

