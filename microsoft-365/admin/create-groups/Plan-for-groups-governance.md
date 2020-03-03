---
title: Planen der Office 365-Gruppen-Governance
ms.reviewer: johasand
f1.keywords:
- NOCSH
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
description: Weitere Informationen zum Planen der Office 365-Gruppen-Governance.
ms.openlocfilehash: b79da69995446aa7e61eea4d836e322743a7d2bb
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352906"
---
# <a name="plan-for-governance-in-office-365-groups"></a>Planen der Governance in Office 365-Gruppen

Office 365-Gruppen verfügt über eine umfangreiche Sammlung von Tools zur Implementierung aller Governance-Fähigkeiten, die Ihre Organisation benötigt. Dieser Artikel leitet IT-Experten an, die richtigen Fragen zu stellen, um ihre Anforderungen an die Governance zu ermitteln und zu bestimmen, wie sie diese auf der Grundlage ihres organisatorischen Profils erfüllen können.

## <a name="why-office-365-groups"></a>Warum Office 365-Gruppen?
![Bildbeschreibung](../../media/01.png)

Wir wissen, dass Organisationen heute ein vielfältiges Toolset verwenden. Es gibt das Entwicklerteam, das den Team-Chat nutzt, die Führungskräfte, die E-Mails versenden, und die gesamte Organisation, die sich über das soziale Netzwerk des Unternehmens verbindet. Es werden mehrere Tools für die Zusammenarbeit verwendet, da jede Gruppe einzigartig ist und ihre eigenen funktionalen Bedürfnisse und ihren eigenen Arbeitsstil hat. Einige werden nur E-Mail verwenden, während andere hauptsächlich im Chat leben. 

Wenn Benutzer das Gefühl haben, dass die von der IT angebotenen Tools nicht ihren Bedürfnissen entsprechen, werden sie wahrscheinlich ihre bevorzugte Verbraucheranwendung herunterladen, die ihre Szenarien unterstützt. Obwohl dieser Prozess den Benutzern einen schnellen Einstieg ermöglicht, führt er zu einer frustrierenden Benutzererfahrung in der gesamten Organisation mit mehreren Anmeldungen, gemeinsamer Nutzung von Schwierigkeiten und keinem einzigen Ort zum Anzeigen von Inhalten. Dieses Konzept wird als "Schatten-IT" bezeichnet und stellt ein erhebliches Risiko für Organisationen dar. Es reduziert die Möglichkeit, den Benutzerzugriff einheitlich zu verwalten, die Sicherheit zu gewährleisten und die Anforderungen an die Einhaltung von Diensten zu erfüllen.

Office 365-Gruppen befähigen die Benutzer und reduzieren das Risiko von Schatten-IT, indem sie in einem einzigen Schritt viele der für die Zusammenarbeit erforderlichen Tools bereitstellen. Sie können mithilfe von Office 365-Gruppen eine Gruppe von Personen auswählen, mit denen Sie zusammenarbeiten möchten, und auf einfache Weise eine Reihe von Ressourcen zum Teilen für diese Personen erstellen. Das manuelle Zuweisen von Berechtigungen zu Ressourcen gehört der Vergangenheit an, da das Hinzufügen von Mitgliedern zur Gruppe automatisch die erforderlichen Berechtigungen für alle von der Gruppe bereitgestellten Objekte erteilt.

## <a name="technical-architecture"></a>Technische Architektur

Office 365-Gruppen unterstützen drei wichtige Kommunikationsmodalitäten. Innerhalb dieser Erfahrungen können Gruppen erstellt und in der Office 365-Suite verwendet werden:
- [Outlook](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2): Zusammenarbeit per E-Mail mit einem freigegebenen Gruppenposteingang und Kalender
- [Microsoft Teams](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2): ein chatbasierter Arbeitsbereich für informelle Unterhaltungen in Echtzeit zu einer Vielzahl von Themen, die nach bestimmten Untergruppen organisiert sind
- [Yammer](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2): unternehmerische soziale Netzwerke für die Zusammenarbeit

> [!NOTE]
> Das Erstellen einer neuen Gruppe über andere Teamwork-Anwendungen wie z. B. SharePoint, Planner oder Stream, schafft eine Gruppe mit einer Outlook-Kommunikationsmodalität mit der Möglichkeit, sich mit Microsoft Teams zu verbinden.

Je nachdem, wo eine Gruppe gegründet wird, werden bestimmte Ressourcen automatisch bereitgestellt, z. B.:
- [Posteingang](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) – Für die E-Mail-Kommunikation zwischen den Mitgliedern Ihrer Gruppe. Dieser Posteingang hat eine E-Mail-Adresse und kann für das Annehmen von Nachrichten von Personen außerhalb der Gruppe und sogar außerhalb Ihrer Organisation konfiguriert werden, ähnlich wie eine herkömmliche Verteilerliste.
 - [Kalender](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) – Für die Planung von Ereignissen im Zusammenhang mit der Gruppe
- [SharePoint-Teamwebsite](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) – Ein zentrales Repository für Informationen, Links und Inhalte, die Ihre Gruppe betreffen
- [SharePoint-Dokumentbibliothek](https://support.office.com/article/share-group-files-749bc73b-90c9-4760-9b6f-9aa1cf01b403) – Ein zentraler Ort zum Speichern und Teilen von Dateien für die Gruppe
- [OneNote-Notizbuch](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) – Für das Sammeln von Ideen, Recherchedaten und Informationen
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) – Für das Zuweisen und Verwalten von Projektaufgaben für die Mitglieder Ihrer Gruppe
- [Yammer-Gruppe](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) – Ein zentraler Ort für Unterhaltungen und für das Teilen von Informationen
- Microsoft Teams – Ein Chat-basierter Arbeitsbereich in Office 365

Wenn Sie mehr darüber erfahren möchten, welche Ressourcen für die einzelnen Gruppen erstellt werden, besuchen Sie [Informationen zu Office 365-Gruppen](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

> [!NOTE]
> Wenn eine neue Office 365-Gruppe über Yammer oder Teams erstellt wird, ist die Gruppe weder in Outlook noch im Adressbuch sichtbar, da die primäre Kommunikation zwischen diesen Benutzern in ihren jeweiligen Clients stattfindet.

> [!IMPORTANT]
> Wenn eine neue Yammer-Gruppe erstellt wird, erstellt die Office 365-Gruppe kein Gruppenpostfach oder eine Kalenderressource. Daher kann eine Yammer-Gruppe nicht mit Microsoft Teams verbunden werden. Siehe [Yammer und Gruppen](https://docs.microsoft.com/yammer/manage-yammer-groups/yammer-and-office-365-groups)

## <a name="where-to-start-a-conversation"></a>Wo man eine Unterhaltung beginnt
Es gibt mehrere Orte für eine Unterhaltung innerhalb von Office 365. Das Verstehen, wo man eine Unterhaltung beginnt, kann Organisationen helfen, eine Kommunikationsstrategie zu definieren.

![Bildbeschreibung](../../media/02.png)

- Teams: Chat-basierter Arbeitsbereich (Zusammenarbeit mit hoher Geschwindigkeit) – innere Schleife
   - Entwickelt für die Zusammenarbeit mit den Personen, mit denen Sie täglich arbeiten
  - Stellt den Benutzern Informationen in einer einzigen Benutzeroberfläche zur Verfügung
  - Hinzufügen von Registerkarten, Connectors und Bots
  - Live-Chat, Audio-/Videokonferenzen, aufgezeichnete Besprechungen.

- Yammer: Verbindung über die Organisation ( Unternehmenssoziales) – äußere Schleife
  - Praxisgemeinschaften – Funktionsübergreifende Gruppen von Menschen, die ein gemeinsames Interesse oder Fachwissen teilen, aber nicht unbedingt tagtäglich zusammenarbeiten
  - Verbindung mit dem Führungsteam, Lerngemeinschaften, rollenbasierte Gemeinschaften

- Outlook Groups – moderne DL (E-Mail-basierte Zusammenarbeit)
  - Allgegenwärtig für gezielte Kommunikation
  - Upgrade von DLs auf Office 365-Gruppen – [Warum sollten Sie ein Upgrade durchführen?](https://support.office.com/article/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

- SharePoint – Grundlegende Informationen zur Zusammenarbeit in allen Office 365-Gruppen
  - Jede Gruppe erhält eine verbundene SharePoint-Teamwebsite
  - Freigeben von Inhalten, Erstellen benutzerdefinierter Seiten und Verfassen von Nachrichten
  - [Verbinden](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview) von bestehenden SharePoint-Teamwebsites mit neuen Office 365-Gruppen

![Bildbeschreibung](../../media/03.png)

##  <a name="managing-and-governing-office-365-at-scale"></a>Office 365 im Maßstab verwalten und leiten

Office 365-Gruppen verfügt über eine umfangreiche Sammlung von Tools zur Implementierung aller Governance-Fähigkeiten, die Ihre Organisation benötigt. Der folgende Abschnitt beschreibt die Möglichkeiten, empfiehlt bewährte Methoden und gibt Hinweise, wie die richtigen Fragen gestellt werden können, um die Anforderungen an die Governance zu bestimmen und wie diese erfüllt werden können.

**In diesem Abschnitt**:
- [Steuern, wer Office 365-Gruppen erstellen kann](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#control-who-can-create-office-365-groups)
- [Vorläufiges Löschen und Wiederherstellen der Gruppe](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-soft-delete-and-restore)
- [Gruppenbenennungsrichtlinie](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-naming-policy)
- [Gruppenablaufrichtlinie](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-expiration-policy)
- [Gruppengastzugriff](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-guest-access)
- [Gruppenrichtlinien und Informationsschutz](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-policies--information-protection)
- [Upgrade herkömmlicher Tools für die Zusammenarbeit](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#upgrade-traditional-collaboration-tools)
- [Gruppenberichterstellung](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#groups-reporting)

### <a name="control-who-can-create-office-365-groups"></a>Steuern, wer Office 365-Gruppen erstellen kann
Gruppen können von Endbenutzern von mehreren Endpunkten aus erstellt werden, einschließlich Outlook, SharePoint, Microsoft Teams und anderen Umgebungen.

![Bildbeschreibung](../../media/04.png)
> [!Tip]
>- Ziehen Sie die Selbstbedienung stark in Betracht, um Gruppenbesitzer zu befähigen.
>- Dokumentieren und teilen Sie mit, wie eine Gruppe angefordert wird.
>- Überprüfen Sie noch einmal, wer während Ihrer Cloud Journey Gruppen erstellen kann.
>- Erwägen Sie die Verwendung einer dynamischen Mitgliedschaft, um die Mitglieder der Sicherheitsgruppe so zu konfigurieren, dass sie die Gruppenerstellung kontrollieren können.
>- Beurteilen Sie, welche Gruppenszenarien über eine dynamische Mitgliedschaft verwaltet werden können und lassen Sie für den Rest die Selbstbedienung zu.

Es gibt drei primäre Modelle der Bereitstellung in Gruppen: Offen, IT-gesteuert oder kontrolliert. In der folgenden Tabelle werden die Vorteile des jeweiligen Modells beschrieben.

| Modell          | Vorteile                                                   |
| -------------- | ------------------------------------------------------------ |
| Offen (Standard) | Benutzer können bei Bedarf ihre eigenen Gruppen erstellen, ohne auf einen IT-Mitarbeiter warten oder einen IT-Mitarbeiter um Hilfe bitten zu müssen. |
| IT-gesteuert         | Benutzer fordern eine Gruppe von der IT an. Die IT kann die Benutzer bei der Auswahl der für ihre Anforderungen am besten geeigneten Tools für die Zusammenarbeit unterstützen. |
| Kontrolliert     | Die Gruppenerstellung ist auf bestimmte Personen, Teams oder Dienste beschränkt. Weitere Informationen finden Sie unter [Verwalten, wer Office 365-Gruppen erstellen kann](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618). |

Ihre Organisation könnte spezifische Anforderungen haben, um strenge Kontrollen darüber einzuführen, wer Gruppen erstellen kann. Verwenden Sie die folgende Tabelle, um die Entscheidung zu erleichtern, welches Bereitstellungsmodell für Ihre Organisation geeignet ist.

|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Welches Bereitstellungsmodell passt zu den Anforderungen Ihrer Organisation?</li><li>Ist für Ihre Organisation die Beschränkung der Gruppenerstellung auf Administratoren erforderlich?</li><li>Ist für Ihre Organisation die Beschränkung der Gruppenerstellung auf Sicherheitsgruppenmitglieder erforderlich?</li><li>Ist für Ihre Organisation, dass einige Gruppen dynamisch auf der Grundlage von Benutzerattributen, wie z. B. Abteilung, erstellt werden erforderlich?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für die Erstellung von Gruppen und Teams.</li><li>Planen Sie, diese Anforderungen als Teil Ihres Gruppen-Rollouts zu implementieren.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um Benutzer über das erwartete Verhalten zu informieren</li><li>Planen Sie ggf. die Einführung einer dynamischen Mitgliedschaft.</li></ul>|

> [!Important]
> Die Einschränkung der Gruppen- und Teamerstellung kann die Produktivität der Benutzer verlangsamen, da viele Office 365-Dienste die Erstellung von Gruppen erfordern, damit der Dienst funktioniert. Weitere Informationen finden Sie unter [Warum soll gesteuert werden, wer Office 365-Gruppen erstellen kann?](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide%23why-control-who-creates-office-365-groups)

#### <a name="resources"></a>*Ressourcen*
- [Verwalten von Personen, die Office 365-Gruppen erstellen können](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide)
- [Dynamisches Auffüllen von Gruppen anhand von Objektattributen](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-with-advanced-rules)
- [So wird die Standardeinstellung von Office 365-Gruppen für Outlook auf "Öffentlich" oder "Privat" geändert](https://support.office.com/article/office-365-groups-in-outlook-private-by-default-36236e39-26d3-420b-b0ac-8072d2d2bedc)
- [Synchronisieren von Sicherheitsgruppen mit der Teammitgliedschaft ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Syncing-Security-Groups-with-team-membership/ba-p/241959)

### <a name="group-soft-delete-and-restore"></a>Vorläufiges Löschen und Wiederherstellen der Gruppe
Wenn Sie eine Office 365-Gruppe gelöscht haben, wird sie standardmäßig noch 30 Tage aufbewahrt. Dieser 30-Tage-Zeitraum wird als "vorläufiges Löschen" bezeichnet, weil Sie die Gruppe immer noch wiederherstellen können. Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.

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
- [Wiederherstellen einer gelöschten Office 365-Gruppe](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54?ui=en-US&rs=en-001&ad=US)
- [Wiederherstellen einer gelöschten Office 365-Gruppe in der Azure Active Directory-Vorschau](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)
- [Löschen von Gruppen mit dem Cmdlet "Remove-UnifiedGroup"](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)

### <a name="group-naming-policy"></a>Gruppenbenennungsrichtlinie
Eine Benennungsrichtlinie kann Ihnen und Ihren Benutzern bei der Identifizierung der Funktion der Gruppe, der Mitgliedschaft, der geografischen Region oder der Person helfen, die die Gruppe erstellt hat. Die Benennungsrichtlinie kann auch hilfreich beim Kategorisieren von Gruppen im Adressbuch sein. Mithilfe der Richtlinie können Sie bestimmte Wörter in Gruppennamen und -aliasen blockieren.

> [!Tip]
> - Verwenden Sie kurze Zeichenfolgen als Namenszusatz.
> - Verwenden Sie Attribute mit Werten.
> - Seien Sie nicht zu kreativ, die Gesamtlänge des Namens beträgt maximal 264 Zeichen.
> - Laden Sie spezifische blockierte Wörter Ihrer Organisation hoch, um die Nutzung einzuschränken.


|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Ist für Ihre Organisation eine bestimmte Benennungskonvention für Gruppen erforderlich?</li><li>Ist für Ihre Organisation die Benennungskonvention für alle Workloads erforderlich?</li><li>Gibt es in Ihrer Organisation bestimmte Wörter, die Sie den Benutzern verbieten wollen?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für die Benennung von Gruppen. </li><li> Planen Sie, diese Anforderungen als Teil Ihres Gruppen-Rollouts zu implementieren.</li><li> Kommunizieren und veröffentlichen Sie die Benennungsrichtlinien und -Standards, um die Benutzer zu informieren.</li></ul>|

> [!Important]
>Die Benennungsrichtlinie wird übergreifend auf Gruppen angewendet, die in allen Workloads (wie Outlook, Microsoft Teams, SharePoint, Planner, Yammer usw.) erstellt werden. Sie wird sowohl auf den Gruppennamen als auch auf den Gruppenalias angewendet. Außerdem wird sie angewendet, wenn ein Benutzer eine Gruppe erstellt und wenn ein Gruppenname oder -alias bei einer bestehenden Gruppe bearbeitet wird.

#### <a name="resources"></a>*Ressourcen*
- [Benennungsrichtlinie für Office 365-Gruppen](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)
- [Erzwingen einer Benennungsrichtlinie für Office 365-Gruppen in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)
- [Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen](https://go.microsoft.com/fwlink/?linkid=868341)
- [Vorschaufeatures für die Gruppenbenennung](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/NamingPolicy)

### <a name="group-expiration-policy"></a>Gruppenablaufrichtlinie
Administratoren können einen Ablaufzeitraum angeben, und jede Gruppe, die das Ende dieses Zeitraums erreicht und nicht verlängert wird, wird gelöscht. Der Ablaufzeitraum beginnt beim Erstellen der Gruppe oder am Datum der letzten Verlängerung. Gruppenbesitzer erhalten vor dem Ablauf automatisch eine E-Mail, die es ihnen erlaubt, die Gruppe für ein weiteres Ablaufintervall zu erneuern.

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
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Muss in Ihrer Organisation ein Ablaufdatum für Teams angegeben werden?</li><li>Ermitteln Sie die Strategie für den Umgang mit verwaisten Gruppen?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation im Hinblick auf Gruppenablauf, Datenaufbewahrung und Archivierung.</li><li>Planen Sie, diese Anforderungen als Teil Ihres Gruppen-Rollouts zu implementieren.</li><li>Planen Sie die Implementierung einer benutzerdefinierten Arbeit, um über Gruppen zu berichten, die über nur einen einzigen oder keinen Besitzer verfügen. </li></ul>|

> [!Important]
>Wenn Sie die Ablaufrichtlinie ändern, berechnet der Dienst das Ablaufdatum für jede Gruppe neu. Er beginnt immer ab dem Datum, an dem die Gruppe erstellt wurde, und wendet dann die neue Ablaufrichtlinie an.

#### <a name="resources"></a>*Ressourcen*
- [Ablaufrichtlinie für Office 365-Gruppen](https://support.office.com/article/Office-365-Group-Expiration-Policy-8d253fe5-0e09-4b3c-8b5e-f48def064733?ui=en-US&rs=en-US&ad=US)
- [Konfigurieren der Ablaufrichtlinie für Office 365-Gruppen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

### <a name="group-guest-access"></a>Gruppengastzugriff
Administratoren können steuern, ob sie den Gastzugriff für Office 365-Gruppen in die ganze Organisation oder für einzelne Office 365-Gruppen zulassen möchten. Sie können auch steuern, wer Gästen ermöglichen kann, zu Gruppen hinzugefügt zu werden.
>[!Tip]
>- Aktivieren des Gastzugriffs auf Mandantenebene. Bei Bedarf, für bestimmte Gruppen blockieren.
>- Verwalten mit Erlauben/Sperren von Gastdomänen, Rolle „Gasteinladender“, Zugangsprüfungen, Nutzungsbedingungen.
>- Nachverfolgen von Gastbenutzeraktivitäten mithilfe von Überwachungsprotokollen.

|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Müssen Sie die Möglichkeit, Gäste zu Teams auf Gruppenbasis hinzuzufügen, einschränken?</li><li> Ist für Ihre Organisation die Vorlage relevanter Haftungsausschlüssen für rechtliche oder Compliance-Anforderungen erforderlich?</li><li>Gibt es in Ihrer Organisation die Notwendigkeit, den Verwaltungsaufwand für das Hinzufügen und Entfernen von Benutzern zu reduzieren?</li><li>Wird in Ihrer Organisation die Kontrolle des Gast-/externen Zugriffs erwartet?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen an den Gast-/externen Zugriff für bestimmte klassifizierte Gruppen, einschließlich der Aufbewahrungszeit und des Auftretens.</li><li>Dokumentieren Sie die Anforderungen der Organisation, für welche Gruppen die Nutzungsbedingungen und die Überprüfung des Zugangs erforderlich sind. </li><li>Führen Sie Überprüfungen durch, um Gruppenmitgliedschaften sowohl für interne als auch für Gastbenutzer effizient zu verwalten.</li></ul>|


#### <a name="resources"></a>*Ressourcen*
- [Verwalten des Gastzugriffs in Office 365-Gruppen](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups)
- [Gastzugriff auf Office 365-Gruppen](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)
- [Gastzugriff auf Office 365-Gruppen – Administratorhilfe](https://support.office.com/article/Guest-access-to-Office-365-groups-Admin-Help-7c713d74-a144-4eab-92e7-d50df526ff96)
- [Zugriffsüberprüfungen in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
- [Nutzungsbedingungsfeature für Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-tou)
- [Verbund mit Google](https://docs.microsoft.com/azure/active-directory/b2b/google-federation)
- [Autorisieren des Gastzugriffs in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-dependencies)

### <a name="group-policies--information-protection"></a>Gruppenrichtlinien und Informationsschutz
Die Office 365-Gruppen basieren auf den erweiterten Sicherheits- und Compliance-Funktionen von Office 365 und unterstützen Klassifizierungen die Überwachung und Berichterstellung, die Compliance-Inhaltssuche, e-Discovery, die gesetzliche Aufbewahrungspflicht sowie und Aufbewahrungsrichtlinien.
>[!Tip]
>- Konfigurieren Sie Klassifizierungen, Verwendungsrichtlinien und Bezeichnungen, die auf die Bedürfnisse Ihrer Organisation abgestimmt sind.
>- Aufbewahrungsrichtlinien können unabhängig von Bezeichnungen definiert werden.
>- Aktivitäten von Überwachungsgruppen: Erstellen, Löschen usw.
>- Verwalten des Datenschutzes und des Gastzugriffs basierend auf der Klassifizierung.

|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Hat Ihre Organisation bestimmte Verwendungsanforderungen, die allen Benutzern mitgeteilt werden müssen?</li><li>Ist für Ihre Organisation die Klassifizierung aller Inhalte erforderlich?</li><li>Ist für Ihre Organisation die Aufbewahrung von Inhalten für einen bestimmten Zeitraum erforderlich?</li><li>Müssen in Ihrer Organisation bestimmte Datenaufbewahrungsrichtlinien auf Gruppen angewendet werden?</li><li>Wird in Ihrer Organisation die Fähigkeit zur Archivierung inaktiver Gruppen gefordert, um den Inhalt zu erhalten?</li><li>Müssen Ersteller von Gruppen in der Lage sein, organisationsspezifische Klassifizierungen für Teams zuzuweisen?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Dokumentieren Sie die Nutzungsrichtlinien Ihrer Organisation für Gruppen</li><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für die Klassifizierung.</li><li>Bestimmen Sie die Richtlinien, die aufgrund der Klassifizierung durchzusetzen sind, z. B. Vertraulichkeit, Aufbewahrung, Gastzugriff.</li><li>Definieren Sie die Vertraulichkeitsbezeichnungen für Ihre Organisation und welche Schutzeinstellungen Sie damit verbinden möchten.</li><li>Definieren Sie eine Bezeichnungsrichtlinie, um zu kontrollieren, welche Benutzer und Gruppen diese Bezeichnungen sehen.</li><li>Konfigurieren Sie die [Vorschau der Gruppenvertraulichkeitsbezeichnung](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) und beginnen Sie, die Gruppen in Ihrer Organisation zu klassifizieren.</li><li>Planen Sie, diese Anforderungen als Teil Ihres Gruppen-Rollouts zu implementieren.</li></ul>|


#### <a name="resources"></a>*Ressourcen*
- [Link zu Nutzungsrichtlinien für Office 365-Gruppen](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [Erstellen von Klassifizierungen für Office-Gruppen in Ihrer Organisation](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- [Konfigurieren der Gruppeneinstellungen](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)
- [Übersicht über Aufbewahrungsrichtlinien](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Übersicht über Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)
- [Übersicht über Bezeichnungen](https://docs.microsoft.com/office365/securitycompliance/labels)
- [Durchsuchen des Überwachungsprotokolls](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance)
- [Erstellen oder Entfernen eines Compliance-Archivs](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)
- [Erstellen einer Erhaltungsrichtlinie](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Ausführen einer Inhaltssuche im Office 365 Security & Compliance Center](https://docs.microsoft.com/Office365/SecurityCompliance/content-search)
- [Massenerstellen und Veröffentlichen von Aufbewahrungsbeschriftungen mithilfe von PowerShell](https://docs.microsoft.com/office365/securitycompliance/bulk-create-publish-labels-using-powershell)

### <a name="upgrade-traditional-collaboration-tools"></a>Upgrade herkömmlicher Tools für die Zusammenarbeit
Jahrelang haben Organisationen mit Verteilergruppen gearbeitet, um mit Personengruppen innerhalb und außerhalb des Unternehmens zu kommunizieren und zusammenzuarbeiten. Office 365-Gruppen in Outlook bieten nun jedoch eine noch leistungsfähigere Lösung für die Zusammenarbeit. Außerdem, die Möglichkeit, eine Office 365-Gruppe mit einer vorhandenen SharePoint-Website zu verbinden, ist wichtig, wenn Sie diese Website modernisieren möchten.

>[!Tip]
>- Aktualisieren Sie alle berechtigten Verteilerlisten in Sekundenschnelle über das Exchange Admin Center oder mithilfe von PowerShell-Cmdlets.
>- Verbinden von bestehenden SharePoint-Teamwebsites mit neuen Office 365-Gruppen.

|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Verfügt Ihre Organisation über Verteilerlisten, die [nicht berechtigt](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists#how-do-i-check-which-dls-are-eligible-for-upgrade) sind, ein Upgrade durchzuführen?<li>Bestimmen Sie, welche Art von Gruppe am besten in die Verteilerliste migriert werden sollte?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Ermitteln Sie, welche Verteilerlisten für ein Upgrade auf Office 365-Gruppen in Frage kämen.</li><li>Analysieren Sie Ihre vorhandenen SharePoint-Teamwebsites, um zu sehen, welche Websites für eine Gruppenverbindung bereit sind.</li><li>Lassen Sie andere Teams in Ihrem Unternehmen wissen, dass Sie Ihre Verteilerliste aktualisiert haben und welche Schritte Sie für eine erfolgreiche Umstellung unternommen haben!</li></ul>|


#### <a name="resources"></a>*Ressourcen*
- [Ausführen eines Upgrades von Verteilerlisten (DL) auf Gruppen in Outlook](https://aka.ms/whyupgradedls):
- [Warum Sie Ihre DL für Gruppen in Outlook aktualisieren sollten](https://aka.ms/whyupgradedls)
- Upgrade mit nur einem Klick über das Exchange Admin Center oder über [PowerShell-Skripts](https://support.office.com/article/Migrate-distribution-lists-to-Office-365-Groups-Admin-help-787d7a75-e201-46f3-a242-f698162ff09f?ui=en-US&rs=en-US&ad=US)
- [Migrieren von Verteilerlisten zu Office 365-Gruppen – Administratorhilfe](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)
- [Verbinden von bestehenden SharePoint-Websites mit Office 365-Gruppen:](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group)
- [Analysieren und Verwenden der Scannerdaten](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group-scanner)
- [SharePoint-Modernisierungsscanner](https://github.com/SharePoint/sp-dev-modernization/tree/master/Tools/SharePoint.Modernization) (ein Tool, das auf GitHub gespeichert ist)

### <a name="groups-reporting"></a>Gruppenberichterstellung
Das Office 365-Dashboard „Berichte“ zeigt Ihnen eine Übersicht über die Aktivitäten in Office 365-Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten.
> [!TIP]
>- Mit dem Gruppenaktivitätsbericht erhalten Sie Einblicke in die Aktivitäten der Office 365-Gruppen innerhalb Ihrer Organisation und erfahren, wie viele Gruppen erstellt und verwendet wurden.
>– Im Bericht Office 365-Gruppen werden die Trends über die letzten 7, 30, 90 oder 180 Tage angezeigt.
>- Überwachen Sie die Gruppenaktivitäten in den Unterhaltungen der Gruppenpostfächer, die Aktivitäten der Gruppenstandorte/Dateien, Details zur Gruppenmitgliedschaft einschließlich der Anzahl externer Mitglieder.
>- Überwachen Sie regelmäßig, um die Gruppenbesitzer aktiver Gruppen zu erreichen, um Anwendungsfälle zu lernen und sie intern zu erweitern.
>- Nutzen Sie Power BI-Inhaltspakete, um weitere Einblicke zu erhalten.


|         |         |         |
|---------|---------|---------|
|![Bildbeschreibung](../../media/decision_point.png)|Entscheidungspunkte|<ul><li>Ist für Ihre Organisation ein regelmäßiger Bericht erforderlich, um die Nutzung von Office 365-Gruppen zu verstehen?<li>Ist für Ihre Organisation eine Berichterstattung über alle Gruppen mit externen Mitgliedern erforderlich?</li></ul>|
|![Bildbeschreibung](../../media/next_steps.png)|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für die regelmäßige Überprüfung von Gruppenaktivitätsberichten.</li></ul>|


#### <a name="resources"></a>*Ressourcen*
- [Office 365-Berichte im Admin Center](https://support.office.com/article/Office-365-Reports-in-the-admin-center-Office-365-groups-a27f1a99-3557-4f85-9560-a28e3d822a40)
- [Inhaltspaket zur Office 365-Einführung](https://support.office.com/article/Office-365-Adoption-Content-Pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)
- [Azure AD-Inhaltspaket](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-power-bi-content-pack-how-to)
- [Microsoft Graph-Gruppenaktivitäts-API](https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/office_365_groups_activity_reports)
- [Office 365-Gruppenbericht (Einheitliche Gruppen)](https://gallery.technet.microsoft.com/office/Office-365-Groups-Report-7e3e161b)
- [Überwachungsaktivitätsberichte im Azure Active Directory-Portal](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-audit-logs)
- [Microsoft Graph – Verwenden einer Delta-Abfrage zum Nachverfolgen von Änderungen](https://docs.microsoft.com/graph/delta-query-overview)

## <a name="getting-started-based-on-your-cloud-adoption-journey"></a>Erste Schritte auf der Grundlage Ihrer Einführung der Cloud Journey

Office 365-Gruppen bietet eine breite Palette von Governance-Fähigkeiten, die Ihre Organisation benötigen könnte. Betrachten Sie die folgenden Organisationsprofile als Orientierungshilfe, um die bewährten Methoden zu verstehen, die richtigen Fragen zu stellen, um die Anforderungen an die Unternehmensführung zu bestimmen, und um herauszufinden, wie diese erfüllt werden können.

**Betrachten Sie die folgenden Organisationsprofile:**
- Kleinunternehmen
- Mittlere Unternehmen
- Reguliert oder Unternehmen

### <a name="small-business"></a>Kleinunternehmen
Ziehen Sie eine Organisation in Betracht, die Office 365 mit mindestens Exchange Online- und SharePoint Online-Lizenzen bereitgestellt hat, welche die Business Essentials- und Business Premium-Pläne sowie die Enterprise E1-, E3- und E5-Pläne ohne Azure Active Director Premium-Lizenz umfasst.

| Stufe 1 | Beschreibung |
| --------------- | ------------------------------------------------------------ |
| Richtlinien |<ul><li>Erwägen Sie ein Selbstbedienungs-Bereitstellungsmodell</li><li> Gruppen in Outlook- und SharePoint-Websites sind [standardmäßig privat](https://techcommunity.microsoft.com/t5/Office-365-Groups/Groups-in-Outlook-and-Group-connected-team-sites-are-now-private/m-p/186395).</li><li> Gruppen können erstellt werden, indem bestehende Verteilerlisten (DLs) entweder einzeln oder in großen Mengen über PowerShell upgraden werden. Siehe [Upgraden von Verteilerlisten zu Office 365-Gruppen](https://support.office.com/article/Upgrade-distribution-lists-to-Office-365-Groups-in-Outlook-787D7A75-E201-46F3-A242-F698162FF09F).</li><li> Aktivieren Sie den Gastzugriff, aber regeln Sie mit Erlauben/Sperren von Gastdomänen.</li><li> Verwenden Sie Gruppenberichte, um Einblicke zu gewinnen, wie Benutzer Gruppen verwenden.</li><li> Erwägen Sie die Schaffung eines organisationsweiten Microsoft Teams-Teams als eine Möglichkeit für alle, Teil eines einzigen Teams für die Zusammenarbeit zu sein. </li></ul>|
| Nächste Schritte      |<ul><li>Erwägen Sie die Verwendung von [Website-Designs und Website-Skripts](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview) zum Definieren des Standardentwurfs für Steuerelemente mithilfe der Aktionen, die in der [JSON-Schemareferenz](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema) definiert sind.</li><li>Überprüfen von [Gruppenberichterstellung](https://support.office.com/article/Office-365-Reports-in-the-admin-center-Office-365-groups-a27f1a99-3557-4f85-9560-a28e3d822a40)</li><li>Nachverfolgen von Gesamtgruppen und inaktiven/aktiven Gruppen</li><li>Nachverfolgen von genutztem Exchange- und SharePoint-Speicher</li><li>Zeigen Sie Gruppenaktivitäten über die Unterhaltungen der Gruppenpostfächer, die Aktivität der Gruppenstandorte/Dateien usw. an.</li></ul> |

### <a name="medium-sized-business"></a>Mittlere Unternehmen
Berücksichtigen Sie zusätzlich zu den obigen Empfehlungen die folgenden Punkte für mittelständische Unternehmen, die Office 365 mit mindestens einer Enterprise E3/E5 mit Azure Active Directory Premium P1-Lizenzen eingesetzt haben.

| Stufe 1 | Beschreibung |
| --------------- | ------------------------------------------------------------ |
| Richtlinien |<ul><li>Entscheiden Sie sich für ein offenes oder IT-gesteuertes Bereitstellungsmodell.</li><li> Erwägen Sie die Schaffung bestimmter Gruppen, die an [dynamische Mitgliedschaftsregeln](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) auf der Grundlage von Azure AD-Attributen wie Abteilung gebunden sind</li><li> Definieren Sie Klassifizierungen innerhalb Ihrer Organisation, z. B. „Hochvertraulich“, „Vertraulich (Standard)“, „Allgemein“.</li><li>  Definieren Sie die Richtlinien auf der Grundlage von Klassifizierungen wie Aufbewahrung und Vertraulichkeit.</li><li> SharePoint ist der Inhaltsdienst für jede Office 365-Gruppe. Erwägen Sie den Entwurf und die [Bereitstellung von SharePoint Online-Websites für drei Schutzebenen](https://docs.microsoft.com/office365/enterprise/deploy-sharepoint-online-sites-for-three-tiers-of-protection) (Basisplan, vertraulich und hochvertraulich). Weitere Informationen zu diesen drei Schutzebenen finden Sie unter [Sichern von SharePoint Online-Websites und -Dateien](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files).</li><li> Öffentliche und private Gruppen werden standardmäßig in der globalen Adressliste (GAL) aufgelistet. Bestimmen Sie, welche Gruppen in der globalen Adressliste erscheinen sollen, insbesondere Gruppen, die außerhalb von Microsoft Teams erstellt wurden.  Verwenden Sie die [Set-UnifiedGroup](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx)-Cmdlets "HiddenFromAddressListsEnabled" oder "HidefromExchangeClients", um bestimmte Gruppen auszublenden </li></ul> |
| Nächste Schritte      |<ul><li>Bestimmen von [Nutzungsrichtlinien](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets), um die Benutzer über die bewährten Methoden zu informieren, die dazu beitragen, die Effektivität der Gruppe zu gewährleisten und interne Inhaltsrichtlinien zu kommunizieren. Beispiel: Grundlegendes zu Klassifizierungen, Richtlinien und Verfahren. </li><li>Bestimmen Sie den Zeitraum des Gruppenlebenszyklus, in dem Gruppen erneuert werden müssen oder gelöscht werden sollen – Ablaufrichtlinie.</li><li>Erwägen Sie die Erstellung der folgenden benutzerdefinierten Aufträge, um Richtlinien basierend auf Klassifizierungen zu implementieren.</li><li>Legen Sie den Datenschutz auf "Privat" fest.</li><li>Externe Mitgliedschaft/Freigabe deaktivieren. </li><li>E-Mail-Nachrichten zur Benachrichtigung von Gruppenmitgliedern für Gruppen [ohne Besitzer](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</li><li>Erzwingen der Besitzrichtlinie (mind. 2 Besitzer)</li><li> Definieren von Aufbewahrungsrichtlinien für Gruppen auf der Grundlage der Klassifizierung. </li><li>Übersicht über Aufbewahrungsrichtlinien.</li><li>Verwenden von PowerShell zum Identifizieren von Gruppen mit einer Klassifizierung und [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps).</li><li>Erwägen Sie die Verwendung von Website-Designs und Website-Skripts zum Definieren der Steuerelemente mithilfe der Aktionen, die in der [JSON-Schemareferenz](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema) definiert sind.</li><li>Erwägen Sie [ein einfaches Websiteverzeichnis mit einem Websitedesign](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-trigger-flow-tutorial) und Microsoft Flow zu erstellen. Wenn Sie eine Website mit diesem Websitedesign erstellen, werden Details zu der Website erfasst und in eine Liste geschrieben. </li></ul>|

### <a name="regulated-or-enterprise"></a>Reguliert oder Unternehmen
Berücksichtigen Sie zusätzlich zu den obigen Empfehlungen die folgenden Punkte für stark regulierte oder große Unternehmen wie Behörden, Finanzdienstleister oder das Gesundheitswesen, die Office 365 mit mindestens einer Enterprise E3/E5 mit Azure Active Directory Premium P1/P2-Lizenzen bereitgestellt haben.

| Stufe 1 | Beschreibung |
| --------------- | ------------------------------------------------------------ |
| Richtlinien |<ul><li> Definieren von Richtlinien für die Daten-Governance der SharePoint-Website, die der Gruppe basierend auf der Klassifizierung zugeordnet ist.</li><li>[Schützen von SharePoint Online-Dateien mit Office 365-Bezeichnungen und Verhindern von Datenverlust](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</li><li>[Schützen von SharePoint Online-Dateien mit Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</li><li> Gruppenstandort, der in einer Region bereitgestellt wird, die an den bevorzugten Datenspeicherort des Benutzers gebunden ist ([Multi-Geo](https://docs.microsoft.com/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365)).</li><li> Mitgliedschaftsüberprüfungen für Gruppen mit externen Mitgliedern ([Zugriffsüberprüfungen](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-access-reviews-overview)).</li><li>Sicherstellen, dass Mitarbeiter oder Gastbenutzer relevante Haftungsausschlüsse angezeigt werden, um rechtliche oder compliancebezogene Anforderungen zu erfüllen. ([Nutzungsbedingungen](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou)).</li><li>Ermitteln und Berichten über Office 365-Gruppen mit einer bestimmten [Klassifizierung, die auch externe Benutzer haben](https://techcommunity.microsoft.com/t5/Office-365-Groups/Sample-Powershell-to-identify-groups-with-HBI-classification-and/m-p/215561).</li><li>Geheime Gruppen, in denen Mitgliedschaften versteckt werden mussten, müssen bei der Gruppenerstellung mit dem Cmdlet [New-UnifiedGroup](https://technet.microsoft.com/library/mt219359(v=exchg.160).aspx) (mit dem Schalter "HiddenGroup-MembershipEnabled") erstellt werden.</li><li>Definieren Sie die [Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels) für die Organisation, um den [Zugriff auf Inhalte einschränken, indem Sie Verschlüsselung verwenden](https://docs.microsoft.com/Office365/SecurityCompliance/encryption-sensitivity-labels) und in bestimmten Office 365-Gruppen veröffentlichen.</li><li>Verhindern, dass vertrauliche Inhalte Ihre Organisation auf Geräten mit Windows verlassen, indem Sie [Vertraulichkeitsbezeichnungen mit Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553) verwenden. |
| Nächste Schritte      | <ul><li> Verwenden Sie Website-Design und Website-Skripts, um die Standard-[Aktionen](https://developer.microsoft.com/office/blogs/site-scripts-site-designs-summer-2018-update/) zu definieren, die beim Erstellen einer neuen Website auftreten. [Konfigurieren Sie beispielsweise die Einstellung für die externe Freigabe](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-apply-external-sharing-setting) oder [lösen Sie einen Microsoft Flow aus, um eine Azure-Funktion aufzurufen](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-azure-function) und Konfigurationen anzuwenden, die nicht nativ unterstützt werden. </li><li> Dokumentieren Sie die Anforderungen zum [Schützen von SharePoint Online-Dateien mit Office 365-Bezeichnungen und Verhindern von Datenverlust](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) auf Websites, die Office 365-Gruppen zugeordnet sind.</li><li>Dokumentieren Sie die Anforderungen der Organisation zum [Sichern von SharePoint Online-Websites und -Dateien](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files), die mit Office 365-Gruppen verbunden sind. </li><li>Dokumentieren Sie die Anforderungen der Organisation zur Veröffentlichung von [Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels) für bestimmte Benutzer oder Gruppen, um den Inhalt zu schützen.</li></ul> |

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
| Ausgeblendete Mitgliedschaft | Blenden Sie die Mitglieder der Office 365-Gruppe vor Benutzern aus, die keine Mitglieder der Gruppe sind | Nein                                    |   Noch nicht festgelegt        |
| Ablaufrichtlinie | Verwalten des Lebenszyklus von Office 365-Gruppen durch das Festlegen einer Ablaufrichtlinie. | P1                                    |  Noch nicht festgelegt        |
| Gruppenaktivitätsberichten | Erhalten Sie Einblicke in die Aktivitäten der Office 365-Gruppen in Ihrer Organisation. Außerdem wird angezeigt, wie viele Office 365-Gruppen erstellt und verwendet werden. | Nein                                    |    Noch nicht festgelegt       |
| Aufbewahrungsrichtlinie | Bewahren Sie Daten für einen bestimmten Zeitraum auf oder löschen Sie diese, indem Sie im Security & Compliance Center Aufbewahrungsrichtlinien für Office 365-Gruppen festlegen. **Hinweis:** Für die Nutzung dieser Funktion ist die Lizenzierung von Office 365 Enterprise E3 oder höher erforderlich. | Nein                                    |    Noch nicht festgelegt       |
| Richtlinie zur Verhinderung von Datenverlust | Identifizieren Sie vertrauliche Informationen in den mit Office 365-Gruppen verbundenen Websites und verhindern Sie die versehentliche Freigabe. **Hinweis:** Für die Nutzung dieser Funktion ist die Lizenzierung von Office 365 Enterprise E3 oder höher erforderlich. | Nein                                    |     Noch nicht festgelegt      |
| Archivieren und Wiederherstellen | Archivieren Sie ein Team, wenn es nicht mehr aktiv ist, Sie es aber zu Referenzzwecken oder zur Reaktivierung in der Zukunft behalten möchten. | Nein                                    |   Noch nicht festgelegt        |
| Zugriffsüberprüfungen | Durchführen von Überprüfungen zum effizienten Verwalten von Gruppenmitgliedschaften sowohl für interne als auch für Gastbenutzer | P2                                    |   Noch nicht festgelegt       |
| Nutzungsbedingungen | Eine einfache Methode damit Organisationen komfortabel Informationen für Endbenutzer anzeigen können. Dadurch wird sichergestellt, dass Benutzern relevante Haftungsausschlüsse angezeigt werden, um rechtliche oder compliancebezogene Anforderungen zu erfüllen. | P1                                    |         Noch nicht festgelegt  |

