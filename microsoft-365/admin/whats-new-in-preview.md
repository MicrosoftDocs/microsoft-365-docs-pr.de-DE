---
title: Was ist neu im Microsoft 365 Admin Center?
f1.keywords:
- CSH
ms.author: anfowler
author: adefowler
manager: shohara
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
- FRP150
description: Microsoft 365 Admin Center – erfahren Sie mehr über die Features, die in diesem Monat hinzugefügt wurden.
ms.custom:
- MACDashWhatsNew
- AdminSurgePortfolio
ms.openlocfilehash: 90805568d77cf55cbd0e77fb3085435df09824ab
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668049"
---
# <a name="whats-new-in-the-microsoft-365-admin-center"></a>Neuerungen im Microsoft 365 Admin Center

::: moniker range="o365-21vianet"

> [!NOTE]
> Einige der Informationen in diesem Artikel gelten möglicherweise nicht für Office 365, die von 21Vianet betrieben werden.

::: moniker-end

Wir fügen [dem Microsoft 365 Admin Center](microsoft-365-admin-center-preview.md)ständig neue Features hinzu, beheben Probleme, die wir kennen, und machen Änderungen basierend auf Ihrem Feedback. Unten können Sie sehen, was heute schon für Sie verfügbar ist. Einige Funktionen werden für unsere Kunden mit unterschiedlicher Geschwindigkeit bereitgestellt. Wenn Sie noch kein Feature sehen, versuchen Sie, [sich der zielgerichteten Version hinzuzufügen](manage/release-options-in-office-365.md).

Und wenn Sie wissen möchten, was mit anderen Microsoft-Cloud-Diensten neu ist:

- [Neuerungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/whats-new)
- [Neuerungen im Exchange Admin Center](https://docs.microsoft.com/Exchange/whats-new)
- [Neuerungen in Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/whats-new)
- [Neuerungen im Microsoft 365 Compliance Center](https://docs.microsoft.com/Office365/SecurityCompliance/whats-new)
- [Neuerungen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)
- [Aktive Websites im SharePoint Online Admin Center](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)
- [Office-Updates](https://docs.microsoft.com/OfficeUpdates/)

## <a name="ignite-2020-august--september"></a>Ignite 2020 (August & September)

Willkommen bei Microsoft Ignite – unserem ersten Online-Ignite. Wir hoffen, Sie in einer unserer Sitzungen zu sehen: [Microsoft Ignite 2020-Sitzungs Katalog](https://myignite.microsoft.com/sessions). Hier sind nur einige der Dinge, über die wir bei Ignite sprechen werden. 
> [!NOTE]
> Nicht alle Features werden sofort für alle verfügbar sein. Wenn Sie die neuen Features nicht sehen, [fügen Sie Targeted Release hinzu](manage/release-options-in-office-365.md).

### <a name="multi-tenant-management"></a>Multi-Mandantenverwaltung

Wir haben eine Reihe von Funktionen für Multi-mandantenadministratoren wie Sie entwickelt, um Ihre Arbeit schneller und effizienter zu machen.

- **Ihre Mandanten**: Wechseln Sie schnell zwischen den Mandanten, die Sie verwalten.
- **Alle Mandanten**: eine neue Seite, auf der Sie schnell die Integrität aller Dienste Ihrer Mandanten, offener Dienstanfragen, Produkte und Abrechnung, Empfohlene Einrichtungsaufgaben und die Anzahl der Benutzer in diesem Mandanten anzeigen können.
- **Setup**: die Seite Multi-Mandanten-Setup zeigt eine Listenansicht der Setup Seite an, die jedoch für viele Mandanten organisiert ist. Sie können sehen, welche Funktionen nicht aktiviert sind, welche Aufgaben für alle Mandanten abgeschlossen werden, Vorgänge, die Mandanten noch ausführen müssen. Diese Ansicht hilft Ihnen, die Funktions Akzeptanz zu überwachen und sicherzustellen, dass die empfohlenen Sicherheitssetup Aufgaben immer ausgeführt werden.
- **Dienst Integrität**: in der Dienst Integritäts Ansicht wird angezeigt, ob sich Vorfälle oder Warnungen auf die Mandanten auswirken. Es wird Ihnen sogar mitteilen, wie viele Ihrer verwalteten Mandanten betroffen sind. Wählen Sie einfach einen Vorfall aus, um weitere Informationen auf der Registerkarte Übersicht zu erhalten, und wechseln Sie dann zur Registerkarte betroffene Mandanten, um einen Drilldown durchführen und diesen Mandanten zu unterstützen.
- Mandanten **übergreifende Postfächer Migrationen** sind jetzt in der öffentlichen Vorschau ein neuer Dienst, mit dem Sie Postfächer zwischen Mandanten verschieben können, ohne dass extern und dann Onboard-Postfächer erforderlich sind. 
- **Mandantenübergreifende Domänen Freigabe**: in Kürze können Sie an einer privaten Vorschau für Funktionen teilnehmen, die es Ihnen ermöglichen, eine Domäne in mehreren Mandanten freizugeben. Wenn Contoso beispielsweise "Flügel Spielzeug" erwirbt, kann Contoso die Domäne mit dem Flügelspiel Spielzeug teilen, damit die Benutzer in beiden Mandanten "contoso.com" als e-Mail-Adressen verwenden können.

![Dienst Integritäts Seite für Mandanten, bei dem ein Vorfall ausgewählt ist und die Registerkarte betroffene Mandanten geöffnet ist. Das Navigationsmenü enthält alle Mandanten, Setup und Dienst Integrität als die einzigen Optionen.](../media/MAC-WN-MTinServiceHealth.png)

### <a name="monitor-your-most-important-accounts"></a>Überwachen Ihrer wichtigsten Konten

Sie können fehlerhafte oder verzögerte e-Mail-Nachrichten, die an Ihre Benutzer mit hohem geschäftlichem Einfluss wie Ihr CEO gesendet werden, überwachen und nachverfolgen. Sie können Prioritäten Konten nachverfolgen, indem Sie Benutzer zu Ihrer Liste mit Prioritäten Konten im Microsoft 365 Admin Center hinzufügen. Hinzufügen von Führungskräften, Führungskräften, Managern oder anderen Benutzern, die Zugriff auf vertrauliche Informationen oder Informationen mit hoher Priorität haben

Prioritäts Konten stehen nur Organisationen zur Verfügung, die die folgenden Anforderungen erfüllen:

- Office 365 E3 oder Microsoft 365 E3 oder Office 365 E5 oder Microsoft 365 E5.
- Mindestens 10.000 Lizenzen und mindestens 50 monatlich aktive Exchange Online Benutzer.

![Setup Seite für das Feature: Überwachen der wichtigsten Konten](../media/MAC-WN-PriorityAccounts.png)

Es gibt zwei Möglichkeiten, um den Einstieg zu erhalten:

- Wechseln Sie zu **Benutzer**, und wählen Sie dann im Menü weitere Aktionen die Option **Prioritäten Konten verwalten** aus, um Benutzer zur Liste hinzuzufügen.
- Wechseln Sie zu **Setup**, suchen Sie nach der Setup Aufgabe **Überwachen Ihrer wichtigsten Konten**, und wählen Sie dann **Erste Schritte** aus.

Weitere Informationen zu Prioritäts Konten finden Sie unter [Monitoring Priority Accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

### <a name="search-faster-and-get-better-results-from-any-page"></a>Schneller suchen und auf jeder Seite bessere Ergebnisse erzielen

Wir haben mit dem Rollout einer neuen Suchumgebung für das Admin Center begonnen, und wir können nicht darauf warten, dass Sie es ausprobieren. ![Das Suchfeld wurde in den Bannerbereich verschoben. Alt + S für die Suche auf einer beliebigen Seite.](../media/MAC-WN-GlobalSearch.png)

- Das Suchfeld wurde in den Kopfbereich verschoben, in dem es "Microsoft 365 Admin Center" heißt, sodass Sie nun von einer beliebigen Seite aus suchen und nicht nur auf der Startseite. Wir haben sogar eine Verknüpfung: **ALT + S**.
- Die Suche ist intelligenter und bietet Ihnen bessere Ergebnisse, sogar noch schneller. Versuchen Sie, "2FA" einzugeben, um loszulegen.
- Suchergebnisse werden nach dem Typ des Elements oder der Aktion organisiert, die Sie ausführen können.
  - **Benutzer**: Wählen Sie den Namen des Benutzers aus, und Sie können diesen Benutzer direkt dort bearbeiten. Wenn Sie das Menü weitere Aktionen neben dem Namen auswählen, können Sie das Kennwort zurücksetzen. Sie können nach Anzeigename, Nachname, Vorname, Benutzername oder primäre e-Mail-Adresse und e-Mail-Aliase suchen. Aber um eine exakte Übereinstimmung zu erhalten, suchen Sie nach primärer e-Mail-Adresse oder Benutzername.
  - **Gruppen**: Bearbeiten Sie die Gruppe von einer beliebigen Seite, fügen Sie Mitglieder hinzu, und weisen Sie Besitzern zu.
  - **Actions**: ähnlich wie Sie nach einem Benutzer suchen und dann Ihr Kennwort zurücksetzen können, können Sie auch "Kennwort zurücksetzen" auf jeder Seite durchsuchen und dann ein oder mehrere Kennwörter für Benutzer zurücksetzen.
  - **Navigation**: mithilfe der Ergebnisse unter Navigation können Sie schnell zu einer Seite im Admin Center gelangen. Wenn Sie beispielsweise "Roles" Durchsuchen, gelangen Sie zur Seite "Rollen" für Azure AD Rollen.
  - **Einstellungen**: Suchen Sie nach beliebigen Einstellungen im Zusammenhang mit Ihrer Organisation, den von Ihnen abonnierten Diensten sowie Sicherheits-und Datenschutzeinstellungen. 
  - **Domänen**: Sie können schnell Links zu Ihren Domänen finden, und dann gelangen Sie über den Link zu der Übersicht und der Integritäts Seite dieser Domäne.
  - **Dokumentation**: Wenn ein Ergebnis für Sie nicht gefunden werden kann, werden wir versuchen, eine Dokumentation zu finden, die Ihnen hilft. Es dauert etwas länger, bis die kuratierte Artikelliste eine Übereinstimmung findet, also warten Sie eine Sekunde, damit die Suche die Ergebnisse findet. 
  - **Feedback**: haben Sie nicht gefunden, wonach Sie gesucht haben? Senden Sie uns Feedback von der Suche. Im Admin Center werden Suchfunktionen für weitere Seiten und mehr Features hinzugefügt.

### <a name="microsoft-365-admin-mobile-app"></a>Microsoft 365 Administrator Mobile App

Mit dem [Microsoft 365-Administrator Mobile App](https://www.microsoft.com/microsoft-365/business/manage-office-365-admin-app), das in Ihrem Abonnement enthalten ist, können Sie Microsoft 365 von Ihrem mobilen Gerät aus verwalten, damit Sie sich von Ihrem Schreibtisch aus für tägliche Aufgaben verlassen können. Tatsächlich gibt es über 90 Features in der APP--und wir haben noch ein paar hinzugefügt:

- **Unterstützung für die Microsoft InTune-Richtlinien für die Verwaltung mobiler Anwendungen und für den bedingten Zugriff**: Sie können jetzt Ihr persönliches Gerät zum Verwalten von Microsoft 365 verwenden, selbst wenn Ihre Organisation die Mobile Anwendungsverwaltung und die bedingten Zugriffsrichtlinien von InTune aktiviert hat.
- **Benachrichtigungen im Nachrichtencenter**: Aktivieren Sie Benachrichtigungen für das Nachrichtencenter unter **Einstellungen**  >   , wenn Sie über neue Nachrichtencenter-Beiträge benachrichtigt werden möchten. Durch Benachrichtigungen möchten wir sicherstellen, dass Sie über wichtige Informationen und Ereignisse in Ihrem Mandanten informiert bleiben.
- Benachrichtigungen zur **Abrechnung**: Sie können Benachrichtigungen auch bei **Einstellungs**  >  **Benachrichtigungen** aktivieren, wenn Sie Abrechnungs Benachrichtigungen auf Ihrem Gerät erhalten möchten, wenn ein Abonnement demnächst abläuft.
- **Dunkler Modus**: Willkommen auf der dunklen Seite des Mobile App. Dies war eines der am häufigsten angeforderten Features. Wechseln Sie zu **Einstellungen**  >  **Designs** , um es zu aktivieren.
- **Ein Problem melden**: Sie können jetzt ein Problem in der APP melden oder von anderen Administratoren gemeldete Probleme anzeigen. Besuchen Sie den **Dienststatus** , um ihn zu überprüfen.

![Die Integritäts Seite in der Microsoft 365-Administrator-App mit Benachrichtigungen für das Nachrichtencenter, Dienststatus, Abrechnungs Benachrichtigungen.](../media/MAC-WN-AdminMobileApp.png)

### <a name="usage-recommendations-for-small-and-medium-businesses"></a>Verwendungsempfehlungen für kleine und mittelständische Unternehmen

Kleine und mittelständische Unternehmen erhalten möglicherweise eine Empfehlung auf der **Start** Seite, wenn einige der Personen in der Organisation keine Teams, OneDrive oder Office-Apps aktiv verwenden. Wenn Sie die Empfehlung anzeigen, können Sie Microsoft Training schnell an inaktive Benutzer senden, damit Sie mit der APP beginnen und sicherstellen, dass Sie den vollständigen Wert aus ihren Abonnements erhalten.

### <a name="remote-work-collection"></a>Remote-Arbeits Sammlung

Im Oktober fügen wir eine Remote-Arbeits Sammlung hinzu, um Besitzern von Kleinunternehmen und deren Mitarbeitern zu helfen, Online zu arbeiten und Remote zu arbeiten.  Das **Remote work Essentials** -Setup ist eine kuratierte Liste aller Features, die Microsoft empfiehlt, Remote-Arbeit sicher zu aktivieren und effektiv zusammenzuarbeiten. In ein paar Wochen können Sie es in **Setup**  >  **Remote work Essentials** ausprobieren.

![Seite "Remote work Essentials" im Setup mit 7 nicht gestarteten Aufgaben.](../media/MAC-WN-RemoteWork.png)

Weitere Informationen zum sicheren zulassen von Remote-Arbeit und eine praktische Webadresse, die sich leicht merken und freigeben lässt, finden Sie unter [aka.ms/Remote-Business](https://aka.ms/remote-business).

### <a name="need-help-moving-to-more-admin-centers"></a>Benötigen Sie Hilfe? Wechseln zu weiteren Verwaltungszentren

Wir untersuchen und aktualisieren die Inhalte und Tools ständig, damit Sie mit den Änderungen im Produkt Schritt halten können. Wir verfügen nun über viele weitere Diagnosetools, die Ihnen helfen, Probleme schnell und effizient zu lösen. Hier sind einige, die vor kurzem hinzugefügt wurden:

- Ändern der Einschränkungsrichtlinie für Exchange-Webdienste
- Überprüfen des Status der Microsoft Teams-Protestierung und Validierung für bestimmte Benutzer
- Beheben von Problemen mit DKIM-Setup
- Diagnostizieren von InTune-Benutzer Registrierungsfehlern

Und wir stellen die neue und verbesserte Supporterfahrung bereit, die Sie bereits im Microsoft 365 Admin Center für einige der anderen Admin Center sehen. Administratoren von Teams und Security and Compliance Admin Center verfügen bereits über diese neue Erfahrung. In Kürze werden die **Exchange-Verwaltungskonsole**, das **SharePoint Admin Center** und **Office.com** mit dieser neuen Hilfe Erfahrung für Administratoren aktualisiert.

### <a name="manage-changes-with-microsoft-planner"></a>Verwalten von Änderungen mit Microsoft Planner

Im Mai haben wir angekündigt, dass Sie bald Nachrichtencenter-Beiträge an Microsoft Planner synchronisieren können und jetzt für alle Benutzer verfügbar sind.  Sie können jetzt Aufgaben aus Nachrichten erstellen, Sie zuweisen und nach Abschluss nachverfolgen. Beim ersten Mal wählen Sie **Planer-Synchronisierung** aus, die Sie zum Herstellen einer Verbindung mit dem entsprechenden Plan benötigen.

![Seite "Nachrichtencenter" mit hervorgehobener "Planer-Synchronisierung" in der Befehlsleiste neben der Schaltfläche "Einstellungen".](../media/MAC-WN-MCPlannerSync.png)

Wenn Sie mehr darüber erfahren möchten, lesen Sie diesen Artikel und das Video, um zu sehen, wie es funktioniert: nach [Verfolgen von Nachrichtencenter-Beiträgen im Planer](https://docs.microsoft.com/Office365/Planner/track-message-center-tasks-planner)

### <a name="documentation-training-and-videos"></a>Dokumentation, Schulung und Videos

- Ganz neu und rechtzeitig für Microsoft Ignite –[der virtuelle Hub](https://adoption.microsoft.com/virtual-hub/). Tiefer Sprung in das technische Training für IT-Experten und Entwickler. Finden Sie schnell rund 20 neue Videos im Rahmen von #SIDETRACKED, dem Namen der Ignite-Administrator-Spur in diesem Jahr.
- [Neuerungen bei Microsoft 365](https://www.youtube.com/watch?v=OVjb2lGJ4GU&t=2s) -Video Serien: in diesem Monat decken wir neue Features ab, die in Whiteboards für Teams und im Internet verfügbar sind, wie Sie die Benutzer Bereitstellung auf Azure AD automatisieren, neue Power-Trigger und-Aktionen in Microsoft Teams automatisieren und vieles mehr. Und bleiben Sie für den nächsten Monat dran, wo wir eine Zusammenfassung aller tollen Dinge bei Ignite haben!
- Wir haben eine Neugestaltung der [Microsoft 365-Dokumentations](https://docs.microsoft.com/microsoft-365) Seite durch geschafft, die sich zunächst auf Lösungen konzentriert. Wir werden neue Lösungen hervorheben, wenn Sie auf dieser Seite verfügbar werden, also halten Sie Ausschau.

![Neue Startseite für Microsoft 365-Lösungsdokumentation mit Lösungen wie "Empower Remote Workers".](../media/MAC-WN-M365Docspage.png)

## <a name="july-2020"></a>Juli 2020

### <a name="getting-ready-for-ignite-2020"></a>Vorbereitungen für Ignite 2020

Während wir in die Ignite Season bei Microsoft umziehen, werden wir nicht so viele Features freigeben, dass wir während unserer Sitzungen viel besprechen müssen.

Das nächste Update für diesen Artikel wird am Tag des ersten Starts unseres ersten Online-ignites sein. In diesem Jahr können Sie kostenlos teilnehmen! Check it out, Get signed up: [Microsoft Ignite 2020](https://www.microsoft.com/ignite).

### <a name="your-products"></a>Ihre Produkte

In der Abonnementverwaltung wurden viele Aufgaben ausgeführt, um die Seite schneller zu laden, schneller zu finden, was Sie suchen, und um die Standards für die Barrierefreiheit im Internet ([WCAG 2,1 Guidelines](http://www.w3.org/TR/WCAG21/)) zu erfüllen.

- **Tabellen Umgestaltung**: die Tabelle wurde neu gestaltet, sodass Sie ähnliche Abonnements gruppieren können. Wechseln Sie zu **Abrechnung**  >  **ihrer Produkte**.
- **Produkt Details**: Weitere Details zu ihren Abonnements erhalten Sie, indem Sie das Produkt in der Liste auswählen.
- **Machen Sie alles von hier aus**: und Sie müssen nicht mehr auf mehrere Seiten wechseln, um ein Produkt zu verwalten. Wenn Sie beispielsweise ein Abonnement stornieren müssen, wird der Bereich geöffnet, um die Aktion direkt dort durchführen zu können.

![Seite "Produkte" mit geöffnetem Abonnement Bereich kündigen.](../media/MAC-WN-SubscrDetails.png)

### <a name="domains"></a>Domänen

Die Domänenverwaltung kann kompliziert sein, und wir haben ein neues Feature veröffentlicht, um es einfacher zu machen. Wechseln Sie zu Einstellungen > Domänen, und wählen Sie dann eine Domäne aus, um weitere Informationen zu Ihrer Domäne und der Domänenintegrität zu erhalten.

:::image type="content" source="../media/MAC-WN-DomainDNS.PNG" alt-text="Seite &quot;Domänendetails&quot; für contoso.com":::

### <a name="docs-training-and-videos-july-2020"></a>Dokumente, Schulungen und Videos (Juli 2020)

[Was ist neu in Microsoft 365](https://youtu.be/m1Nu8WJgCDY) Video Series: in diesem Monat decken wir die neue Jammer Erfahrung für das Internet und Mobile, die Integration der Jammer Gemeinschaften-App für Microsoft Teams, neue Richtlinien Pakete zur Unterstützung von Mitarbeitern und Führungskräften in erster Linie und vieles mehr.

## <a name="june-2020"></a>Juni 2020

### <a name="keeping-up-with-office-whats-new-management"></a>Schritt halten mit Office What es New Management

Vor ein paar Monaten haben wir eine Einstellung hinzugefügt, mit der Sie die neuen Nachrichten verwalten können, die [in den Office-Apps eines Benutzers angezeigt](#office-whats-new-management)werden. In diesem Monat haben wir eine neue Homepage-Karte veröffentlicht, mit der Sie schnell handeln und die **neuen** Nachrichten verfolgen können, die den Benutzern in Ihrer Organisation angezeigt werden sollen.

### <a name="docs-training-and-videos-june"></a>Dokumente, Schulungen und Videos (Juni)

- [Erste Schritte mit Microsoft Teams](https://support.microsoft.com/office/184f1aba-2f91-43f0-86e1-9fae607e24f6)

## <a name="may-2020"></a>Mai 2020

### <a name="new-update-channel-for-office"></a>Neuer Update Kanal für Office

Am 12. Mai kündigten wir die Verfügbarkeit eines neuen Update Kanals für Office an: Monthly Enterprise Channel. Dieser Update Kanal stellt Ihren Benutzern neue Office-Funktionen einmal monatlich am zweiten Dienstag des Monats zur Verfügung.

Wenn Sie den Benutzern die Selbstinstallation von Office über das Portal gestatten, können Sie für diese Benutzer den monatlichen Enterprise-Kanal auswählen. Um dies zu tun, melden Sie sich beim Microsoft 365 Admin Center an, und wechseln Sie zu **alle Einstellungen anzeigen**  >   >  **org Settings**  >  **Services**  >  **Office Software Download Settings**. Wenn Sie **einmal monatlich (monatlicher Enterprise-Kanal)** auswählen, werden alle neuen selbst Installationen von Office für die Verwendung des monatlichen Enterprise-Kanals konfiguriert.

In Verbindung mit der Veröffentlichung des monatlichen Enterprise-Kanals überarbeiten wir auch die Namen der vorhandenen Update Kanäle. Beispielsweise wird der monatliche Kanal in den aktuellen Kanal umbenannt. Die neuen Namen werden am 2020. Juni wirksam.

Weitere Informationen finden Sie unter [Changes to Update Channels for Microsoft 365 apps](https://docs.microsoft.com/DeployOffice/update-channels-changes).

### <a name="new-admin-roles"></a>Neue Administratorrollen

Wir haben einige neue Azure Active Directory Administratorrollen zum Microsoft 365 Admin Center hinzugefügt.

- Die Administratorrolle "Hybrid Identity" gibt Benutzern die Berechtigung zum Verwalten von Cloud-Bereitstellungs-und Authentifizierungsdiensten.
- Die Rolle "Netzwerkadministrator" ermöglicht Benutzern das Verwalten von Netzwerkstandorten und das Überprüfen von Netzwerk Einblicken für Microsoft 365-Software als Dienst apps.
- Die Druckeradministrator Rolle erteilt die Berechtigung zum Verwalten aller Aspekte von Druckern und Druckerverbindungen.
- Der Drucker Techniker ist eine Teilmenge der Druckeradministrator Rolle, mit der diese Benutzer Drucker registrieren und aufheben können, und Aktualisieren des Druckerstatus.
Weitere Informationen zu diesen Rollen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

### <a name="export-groups-list"></a>Liste "Gruppen exportieren"

Wir haben viele Administratoren gehört, dass Sie Informationen über Gruppen und deren Nutzung für Personen freigeben müssen, die keinen Zugriff auf die Admin Center haben. Sie können die Gruppenliste nun zu Überwachungszwecken in eine CSV-Datei exportieren, was bedeutet, dass Sie das alte PowerShell-Skript auswerfen können. Um es auszuprobieren, wechseln Sie zu **Gruppen**  >  **Gruppen**, und wählen Sie dann in der Befehlsleiste **Gruppen exportieren** aus.

### <a name="microsoft-365-solution-and-architecture-center"></a>Microsoft 365-Center – Lösungen und Architekturen

In diesem Monat haben wir eine neue Website mit dem [https://docs.microsoft.com](https://docs.microsoft.com) Namen " [Microsoft 365 Solution and Architecture Center](https://docs.microsoft.com/microsoft-365/solutions/solution-architecture-center)" veröffentlicht, in der die technischen Anleitungen zum Verständnis, zur Planung und zur Implementierung integrierter Microsoft 365-Lösungen für eine sichere und konforme Zusammenarbeit zusammengefasst werden. In diesem Center finden Sie:

- Grundlegende Lösungsanleitungen
- Arbeits Auslastungs Lösungen und Szenario-Anleitungen
- Lösungs-und Architektur Illustrationen (Poster!!!)
- Branchenspezifische Anleitungen
- Entwurfs Prinzipale für die Unternehmensarchitektur

### <a name="docs-training-and-videos-may"></a>Dokumente, Schulungen und Videos (Mai)

- **Was ist neu in Microsoft 365 Video Series**: diesen Monat decken wir die neue Supporterfahrung in den Teams admin und Security and Compliance Center, Planner Integration in das Nachrichten Center und das neue 3X3-Video Layout in Microsoft Teams ab. 
- Die Seite [Microsoft 365 Admin Center Help](https://docs.microsoft.com/microsoft-365/admin/) Hub wurde aktualisiert, um Ihnen zu helfen, schneller zu finden, was Sie benötigen. Wenn Sie diese Seite jetzt betrachten, haben wir eine Karte hinzugefügt, um Sie über wichtige Updates und Änderungen zu informieren.

## <a name="april-2020"></a>April 2020

### <a name="intune-roles-management"></a>InTune-Rollenverwaltung

[April 2020](#april-2020)

Nun, wir haben es geschafft! Wir haben den zweiten Schritt hin zu einer einheitlichen Rollen Erfahrung unternommen, und Sie können jetzt InTune-Rollen im Microsoft 365 Admin Center verwalten. Sie können auch Features wie die Suche nach Rollen und das Anzeigen von Rollen Berechtigungen nutzen. Dies bedeutet, dass Sie nicht zwei separate Tools zum Verwalten von Rollen für Microsoft 365 und InTune benötigen. Wenn Sie sich beim Microsoft 365 Admin Center anmelden, sehen Sie, dass auf der Seite "Rollen" zwei Pivots vorhanden sind: eine für Azure AD und eine für InTune.

![Rollen Seite mit ausgewähltem InTune-Pivot](../media/MAC-WN-IntuneRoles.png)

### <a name="sync-message-center-posts-to-planner"></a>Nachrichten Center-Beiträge für Planer synchronisieren

Ab Mai beginnen Administratoren, die sich in der gezielten Version befinden, die Schaltfläche "Planer synchronisieren" im Nachrichtencenter. Sie können jetzt Nachrichten nachverfolgen, die eine Aktion erfordern, den Nachrichtentyp auswählen, den Sie nachverfolgen möchten, Nachrichten nachverfolgen als Aufgaben zuweisen und Nachrichten zur späteren Beachtung markieren.

[Join Targeted Release](manage/release-options-in-office-365.md) to Get Started!

### <a name="need-help-launched-in-teams-admin-center--security-and-compliance-centers"></a>"Benötigen Sie Hilfe?" gestartet in Teams Admin Center & Security and Compliance Center

Das Teamadministrator Center, das Sicherheitscenter und das Compliance Center verwenden nun dieselbe "Hilfe benötigen?" Feature, das im Microsoft 365 Admin Center zum Suchen von Hilfe und zum Kontaktieren des Supports verwendet wird. Wir haben viele Feedbacks von Administratoren erhalten, dass Sie das gleiche Maß an Hilfe und Unterstützung wünschen, und wir freuen uns, Ihnen das zu bringen. Probieren Sie es aus und geben Sie uns Ihr Feedback!

#### <a name="need-chat"></a>Benötigen Sie einen Chat?

Unsere Support-Agents haben von zu Hause aus gearbeitet und trotzdem Kundenanfragen und Einschränkungen bei der Internet Bandbreite bei der Arbeit von zu Hause aus beeinflussen, können die Kundenanruf Qualität beeinträchtigen. Um Sie weiterhin zu unterstützen, haben wir die Live Chat Unterstützungs Option für kommerzielle Kunden im Microsoft 365 Admin Center gestartet.

Beim Erstellen einer Dienstanforderung wird nun zusätzlich zu Telefon und e-Mail Chat als Option angezeigt. Wählen Sie Chat als bevorzugten Kommunikationskanal aus, und erstellen Sie die Anforderung. Nachdem Sie die Anforderung erstellt haben, können Sie mit dem Chat beginnen, wenn Sie zum chatten mit Microsoft Agents fähig sind.

### <a name="teams-updates"></a>Microsoft Teams-Updates

Durch die verstärkte Nutzung von Teams haben wir einige Features hinzugefügt, die Ihnen bei der Verwaltung helfen.

- Eine neue Empfehlungskarte auf der Admin Center-Startseite zeigt an, welche Benutzer Microsoft Teams nicht 30 Tage lang aktiv verwendet haben. Sie können diesen Benutzern eine Schulungs-e-Mail senden, um die Verwendung von Microsoft Teams zu starten.
- **Zusammenführen von Personen mit Microsoft Teams**: Wechseln Sie zu **Setup** , um eine neue Seite zu sehen, die Sie beim Aktivieren von Teams für lizenzierte Benutzer und beim Zulassen von Gastzugriffen unterstützt, damit Sie mit externen Kunden in Teams arbeiten können.
- Eine Microsoft Teams-Karte ist jetzt standardmäßig auf Ihrer Startseite fixiert. Sie zeigt an, ob Microsoft Teams aktiviert ist und ob Gastzugriff zulässig ist. Außerdem können Sie den Installationsstatus für neu lizenzierte Microsoft Teams-Benutzer überprüfen und überprüfen, ob sich Netzwerkprobleme auf die Benutzer von Microsoft Teams auswirken können.
- Schließlich ist Microsoft Teams nun ein Schritt im ersten Setup-Ablauf, wenn Sie eine Lizenz erworben haben, die Teams enthält.

### <a name="productivity-score"></a>Produktivitäts Bewertung

Die Produktivitäts Bewertung gibt Einblicke in die Verwendung von Microsoft Cloud-Diensten und die Technologie Erfahrungen, die Sie unterstützen. Die Bewertung spiegelt die Leistung Ihrer Organisation anhand von Maßnahmen zur Mitarbeiter-und Technologie Erfahrung wider und vergleicht Ihre Bewertung mit Organisationen wie Ihrem. In diesem Monat führen wir die folgenden neuen Konzepte in die Vorschau ein:

- Trend Ansicht von primären Einblicken auf Homepage und Kategorie-Detailseiten-Endpunktanalyse und Netzwerk Verbindungskategorien wurden der Technologie Oberfläche hinzugefügt
- Relevante Technologie Erfahrungs Einblicke in den Kategorien "Mitarbeiter Erfahrung"
- Neue Kategorie "Kommunikation" im Rahmen der Mitarbeiter Erfahrung
- Benutzer Details mit Organisations Metadaten in den Kategorien "Mitarbeiter Erfahrung"

Wenn Sie mehr erfahren möchten, lesen Sie den Blog: [Messen und verbessern Sie die Microsoft 365-Erfahrung mit Microsoft Productivity Score](https://techcommunity.microsoft.com/t5/microsoft-365-blog/measure-and-improve-the-microsoft-365-experience-with-microsoft/ba-p/1348618). Das Produktivitäts Ergebnis befindet sich derzeit in privater Vorschau. [Treten Sie der privaten Vorschau für Produktivitäts Bewertungen](https://aka.ms/productivityscorepreview) bei, um loszulegen.

### <a name="groups-updates"></a>Gruppen Aktualisierungen

Wir haben zwei Updates für Gruppen in diesem Monat:

- Sie können nun e-Mail-Adressen für Office 365 Gruppen (auch Gruppen in Outlook und bald als Microsoft 365-Gruppen bezeichnet) bearbeiten.
- Wir haben Ihr Feedback gehört und wir haben klarer Fehlermeldungen hinzugefügt, warum Sie eine Gruppe nicht in ein Microsoft-Team konvertieren können.

### <a name="docs-videos-and-training-april"></a>Dokumente, Videos und Schulungen (April)

**Was ist neu in Microsoft 365 Video Series**: diesen Monat decken wir Tipps und Ressourcen ab, um kleinen Unternehmen den Übergang zu Remote-Arbeit zu erleichtern, einschließlich der Bereitstellung von Microsoft Teams, Remote-Arbeits Schulungsressourcen, um mit Kunden und Partnern in Verbindung zu bleiben, und dem neuen Business Voice-Plan von Microsoft 365. [Neuerungen in Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

#### <a name="for-your-users"></a>Für Ihre Benutzer

- [Planen einer Besprechung](https://support.microsoft.com/office/c61b4f61-ee62-4a06-8bf7-0a1cd302700a)
- [An einer Microsoft Teams-Besprechung teilnehmen](https://support.microsoft.com/office/078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [Erstellen eines organisationsweiten Teams](https://support.microsoft.com/office/037bb27a-bcc9-48fe-8d72-44d9482420a3)
- [Erstellen Sie ein Team mit Gästen](https://support.microsoft.com/office/11fbb083-52ee-434d-8c6e-63711fdafac7)
- [Als Gast an einem Team teilnehmen](https://support.microsoft.com/office/928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Erstellen einer Gruppen-e-Mail-Adresse](https://support.microsoft.com/office/ded875f9-a9de-437f-b559-2ae4f235bb2b)

#### <a name="for-admins-and-business-owners"></a>Für Administratoren und Unternehmer

- [Remotearbeit kann auch Ihrem Kleinunternehmen weiterhelfen](https://support.microsoft.com/office/9b91a85a-39b4-40a6-a590-0f9bea0ba8e6)
- [Führen eines Remote-Kleinunternehmens](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [Registrieren für Microsoft Business Basic](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [Einrichten der zweistufigen Anmeldung](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)

## <a name="march-2020"></a>März 2020

### <a name="featured-feedback-fix-improve-add-user-reliability-for-licensing"></a>Featured Feedback Fix: verbessern der Zuverlässigkeit von "Benutzer hinzufügen" für die Lizenzierung

Wir haben viel Feedback von Administratoren erhalten, wie schwer es ist, beim Hinzufügen von Benutzern Lizenzen zuzuweisen. Wir haben das erste Update für diesen Fix durchgeführt, und wir haben zu einem zuverlässigeren Behind-the-Scenes-Dienst migriert, um diese Anforderungen zu verarbeiten. Wenn etwas schief geht, erhalten Sie nun eine Fehlermeldung, mit der Sie es erneut versuchen können.

![Benutzer Bestätigungsseite mit dem Fehler hinzufügen.](../media/MAC-WN-ImprovedLicensing.png)

### <a name="microsoft-teams-home-page-card"></a>Microsoft Teams-Startseite-Karte

Mit dem Uptick in Teams-Nutzung erhalten einige Organisationen eine angeheftete dashboardkarte, die das Umwandeln von Teams auf mehr auffindbar macht. Die Karte enthält auch Links zu Schulungen und Dokumenten, die ihren org-Übergang zu Remote-Arbeit erleichtern. Wechseln Sie einfach zur **Start** Seite, um die neue Karte anzuzeigen.

![Microsoft Teams-Startseite-Karte](../media/MAC-WN-TeamsCard.PNG)

### <a name="customize-your-organizations-sharepoint-mobile-app-theme"></a>Anpassen des SharePoint Mobile App Designs in Ihrer Organisation

Mit dem Microsoft 365 Admin Center können Sie nun das Design Ihrer Organisation in SharePoint Mobile App für IOS und SharePoint Mobile App für Android anpassen. Dieses Feature bietet bequem eine Mobile Intranet-APP, die mit Ihrem SharePoint Online für Mitarbeiter unterwegs übereinstimmen kann. Die Design Anpassung umfasst das Logobild, die Farbe der Navigationsleiste, Text-und Symbol Farben sowie Akzentfarben, wodurch die Erkennung vereinfacht wird.

![Diagramm, das die Admin Center-Einstellungen dem Mobile App zuordnet.](../media/MAC-WN-CustThemeSP.png)

### <a name="improvements-to-the-add-a-group-wizard"></a>Verbesserungen am Assistenten zum Hinzufügen einer Gruppe

Wenn Administratoren eine neue Gruppe erstellt haben und Sie gleichzeitig zu einem Team gemacht haben, können Sie Besitzern zuweisen, die nicht über eine Lizenz mit Teams verfügen. Und das verursachte Kopfzerbrechen. Wir haben den Assistenten Ablauf aktualisiert, um sicherzustellen, dass Besitzer eine Microsoft Teams-Lizenz besitzen und wenn Sie nicht die Möglichkeit haben, die Gruppe in ein Team zu verwandeln, ist deaktiviert.

### <a name="microsoft-365-offerings-for-small-and-medium-businesses"></a>Microsoft 365-Angebote für kleine und mittelständische Unternehmen

Wir wissen, dass dies eine Ankündigung für den nächsten Monat ist, aber wir möchten sicherstellen, dass Sie bereit sind.

Ab dem 21. April nehmen wir Änderungen in Bezug auf unsere Office 365 Abonnements für kleine und mittelständische Unternehmen – und Office 365 ProPlus vor. Für diese Produkte wird nun die Marke Microsoft 365 verwendet.

Die neuen Produktnamen treten am 21. April 2020 in Kraft. Dies ist nur eine Änderung am Produktnamen, und derzeit gibt es keine Preis-oder Funktionsänderungen.

|Aktueller Name |Neuer Name  |
|---------|---------|
|Office 365 Business Essentials     |   Microsoft 365 Business Basic      |
|Office 365 Business Premium     |    Microsoft 365 Business Standard     |
|Microsoft 365 Business     |    Microsoft 365 Business Premium     |
|Office 365 Business     |    Microsoft 365 Apps for Business       |
|Office 365 ProPlus    |   Microsoft 365-Apps für Unternehmen      |

### <a name="videos-training-and-docs"></a>Videos, Schulungen und Dokumente

[Neuerungen in Microsoft 365-Webreihen](https://go.microsoft.com/fwlink/p/?linkid=2118096): in der Episode dieses Monats heben wir das dreijährige Jubiläum von Microsoft Teams hervor und decken neue Features ab, darunter eine verbesserte Audioqualität in Onlinebesprechungen, eine gezielte Kommunikation für First Line-Manager mit der "Shifts"-App, Teams und Skype Consumer-Interoperabilität und vieles mehr.

## <a name="february-2020"></a>Februar 2020

### <a name="featured-feedback-fix-multi-organization-switcher"></a>Featured Feedback Fix: Multi-Organization Switcher

Wir haben viel Feedback von Partnern und Administratoren über die Herausforderungen bei der Verwaltung mehrerer Microsoft Cloud-Organisationen erhalten. Eine unserer ersten Multi-org-Verwaltungsfunktionen ist der **Organisations Umschalter**, mit dem Sie zwischen den Organisationen wechseln können, die Sie in nur 2 Klicks verwalten.
> [!TIP]
> Sie müssen nichts tun, damit die Organisations Umschaltung angezeigt wird, solange Sie der Partner von Record für mindestens eine Organisation sind.

1. Wählen Sie im Microsoft 365 Admin Center den Namen der Organisation aus.
![Screen Capture: oben auf der Startseite wird der Name des Organisationsprofils mit dem Switcher-Symbol angezeigt.](../media/MAC-Organization-switcher.png)

2. Wählen Sie im Organisations Wechsler die org aus, die Sie verwalten möchten.
![Screen Capture: mein Organizations-Mandanten Switcher mit konsolidiertem Messenger-Mandanten hervorgehoben](../media/MAC-OrgSwitcherSelected.png)

Das ist buchstäblich!!!

### <a name="groups"></a>Gruppen

Ein paar Änderungen im Gruppenbereich in diesem Monat:

- **Sortieren nach Gruppenname**: Sie können die Gruppenliste alphabetisch sortieren, indem Sie die Spalte **Gruppenname** auswählen.
- **Wiederherstellen gelöschter Microsoft 365-Gruppen**: Sie müssen nicht mehr zum Exchange-Verwaltungskonsole wechseln, um gelöschte Microsoft 365-Gruppen wiederherzustellen. Wechseln Sie zu **Microsoft 365 Admin Center** \> **Gruppen** \> **Gelöschte Gruppen** \> (Wählen Sie eine Gruppe aus der Liste aus) \> **Restore Group**. Dadurch wird die Gruppe wieder in der **Gruppen** Liste wiederhergestellt und die e-Mails, Unterhaltungen, das Notizbuch, die Dateien und den Kalender der Gruppe wiederhergestellt.

### <a name="videos-training-and-docs-february"></a>Videos, Schulungen und Dokumente (Februar)

- **Neuerungen in der Microsoft 365-Videoreihe**: in diesem Monat konzentrieren wir uns auf benutzerdefinierte Suchfunktionen für SharePoint Online, das Office-Verwaltungsfeature "What es New", mit dem Sie bestimmte Features von Endbenutzern über den in-App-Hilfebereich, die neuesten Sicherheits-und Kompatibilitätsupdates in jammern oder mehr anzeigen oder ausblenden können. Hier ist die neueste Episode: [Neuerungen in Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

- **Docs-Bewegung**: Wir haben die Office 365 admin-Webartikel mit dem Microsoft 365-Inhalt kombiniert, und Sie haben möglicherweise die neue URL bemerkt. Dieser Artikel wurde beispielsweise unter: **docs.Microsoft.com/Office365/admin/Whats-New-in-Preview** gehostet, aber die URL lautet jetzt: **docs.Microsoft.com/Microsoft-365/admin/Whats-New-in-Preview**. Wenn Sie Seiten mit einem Lesezeichen versehen haben, sollten Sie Ihre Links aktualisieren; Inhaltslinks werden jedoch an das neue Content Repo umgeleitet.

## <a name="january-2020---happy-new-year"></a>Januar 2020-Happy New Year

> [!NOTE]
> Wussten Sie, dass es ein [Neuerungen in der Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096) -Videoreihe auf YouTube gibt? Es werden die neuesten Features hervorgehoben, die für die Benutzer bereit stehen. Jeden Monat beginnen wir mit der Verknüpfung mit der neuesten Episode im Abschnitt [Videos, Schulungen und Dokumente](#videos-training-and-docs) . <br> <br> Hier ist die neueste Episode: [Neuerungen in Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

### <a name="dark-mode"></a>Dunkler Modus

Wenn wir den dunklen Modus zum ersten Mal ausgeführt haben, war er nur auf der Startseite verfügbar. Der dunkle Modus ist jetzt nicht mehr in der Vorschau und wird für die meisten Seiten im Admin Center in einer gezielten Version veröffentlicht.

1. Zunächst müssen Sie Targeted Release aktivieren: Wechseln Sie zu Einstellungen Einstellungen  \>  \> **Organisationsprofil** \> - **Freigabe** Einstellungen.
1. Um dann den dunklen Modus zu aktivieren, wechseln Sie zur **Start** Seite, und wählen Sie dann die Schaltfläche **dunkler Modus** aus. (Er befindet sich neben dem **Suchfeld** und diesem Artikel **What es New** Link.)
1. Für jede Seite, auf der der dunkle Modus verfügbar ist, befindet sich die Schaltfläche oben auf der Seite neben **dem neuen Admin Center** -Toggle.

### <a name="office-whats-new-management"></a>Office What es New Management

Administratoren möchten steuern, wie Microsoft "What es New" für Ihre Benutzer in den Office-Apps kommuniziert – und Sie verfügen nun über diese Kontrolle. Wechseln Sie zu **Einstellungen** in \> **Office What es New Management Preview**. Wählen Sie ein Feature aus, um die Details anzuzeigen, und klicken Sie dann auf die Schaltfläche **von Benutzern ausblenden** , wenn Sie nicht möchten, dass Ihre Benutzer eine bestimmte Nachricht "What es New" anzeigen können. Beispielsweise kann es sein, dass Ihre Organisation darauf wartet, dass Benutzer über ein Feature informiert werden, bis alle Personen in Ihrer Organisation darauf geschult sind.

![Bildschirmaufzeichnung von Office What es New Preview mit dem Detailbereich eines Features geöffnet.](../media/whatsnew-officemgmt-preview.png)

Dieses Feature wurde erstmals für die Vorschau im November veröffentlicht, aber es wurden einige Feature-Updates vorgestellt, die Sie kennen sollten: [Office What es New Management Preview Updates now available](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-preview/ba-p/1020438)

### <a name="partners"></a>Partner

Howdy, Partner! (Konnte mir nicht helfen.) Wir haben auch in diesem Monat ein Update für Sie. Es gibt ein neues Feature, das es Partnern ermöglicht, CSP-Kunden die Möglichkeit zu geben, Ihre Microsoft-Kundenvereinbarung (MCA) im Abschnitt " **Abrechnungskonten** " des Admin Centers anzunehmen. In dieser neuen Erfahrung:

1. Der Kunde erhält eine Einladungs-e-Mail mit einem Link, um die Partnerbeziehung und das MCA zu akzeptieren.
2. Nachdem sich der Kunde angemeldet hat, kann er die MCA-und Partner Berechtigungen-rechts über das Admin Center anzeigen und akzeptieren.

### <a name="resource-mailboxes"></a>Ressourcenpostfächer

Die Liste mit den Ressourcenpostfächern wurde auf die neue Formatvorlage aktualisiert. Wechseln Sie im Microsoft 365 Admin Center zu **Ressourcen** \> **Räume & Equipment**.

### <a name="videos-training-and-docs-january"></a>Videos, Schulungen und Dokumente (Januar)

Schauen Sie sich die Administratoren Schulung für kleine Unternehmen an, die wir im Januar veröffentlicht haben:

- [Erstellen Ihrer Website für Unternehmen](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9)
- [Suchen nach Antworten und Hilfe](https://support.microsoft.com/office/7f681212-c649-4a3e-a43b-32b1d1e58988)
- [Hilfe oder Support erhalten](https://support.microsoft.com/office/18948a4c-3eb1-4b30-b1bc-a4cc29eb7655)
- [Benutzer löschen](https://support.microsoft.com/office/6bcdad7b-732a-4260-997a-8c176bc3d9d6)
- [Auswählen eines Microsoft-Abonnements](https://support.microsoft.com/office/b9f7c78e-430f-4117-89ec-2eeb1dced2ca)
- [Übersicht über Microsoft 365 for Business-Sicherheit](https://support.microsoft.com/office/3274b159-a825-46d7-9421-7d6e209389d1)

## <a name="november-and-december-2019"></a>November und Dezember 2019

Wir kombinieren die Neuigkeiten von November und Dezember, da wir nach dem entzünden nur sehr wenige Ankündigungen zu machen hatten. Wir sehen uns im neuen Jahr!

### <a name="change-from-credit-card-to-invoice-payment"></a>Wechsel von der Kreditkarte zur Rechnungszahlung

Wir beginnen mit dem Rollout der Möglichkeit, Ihre Zahlungsmethode von Kreditkarte zu einer Rechnung zu ändern. Wechseln Sie zu **Fakturierung** \> **ihrer Produkte**, wählen Sie ein Abonnement aus, und wählen Sie dann den Link **Bearbeiten** neben der Kreditkartenzahlung aus.

![Screen Capture: Abrechnungs Abschnitt der Abonnementkarte mit einer Kreditkarte als Zahlungsmethode.](../media/MAC-BillingEditCreditCard.png)

Möchten Sie mehr darüber erfahren? [Ändern der Zahlungsmethode von per Kreditkarte zu per Bankkonto oder auf Rechnung](../commerce/billing-and-payments/change-payment-method.md)

### <a name="global-reader"></a>Globaler Leser

Wir haben die Rolle des globalen Lesers in der [Oktober 2019-Ignite-Edition](#october-2019---ignite-edition)erwähnt, aber da Sie im allgemeinen weiter kommt, lassen Sie uns einige Details besprechen:

- Die globale Leserrolle ist das schreibgeschützte Pendant zur globalen Administratorrolle. Der globale Leser kann alles sehen, wozu der globale Administrator berechtigt ist.
- Mit einigen wenigen Ausnahmen, wie einige Compliance-und Sicherheitsfunktionen, haben globale Leser Zugriff auf alle Microsoft Cloud-Verwaltungszentren, die Ihre Organisation für die Verwendung lizenziert hat.
- Zuweisen der globalen Leserrolle zu Benutzern, die Sie für die Planung, Überwachung und Untersuchung benötigen.
- Sie können auch die globale Leserrolle mit einer anderen Rolle kombinieren, die über weniger Berechtigungen verfügt. Beispielsweise kann einem Besitzer eines kleinen Unternehmens die globalen Leser Rollen für die **Fakturierungs Verwaltung** zugewiesen werden,  +   damit er die Rechnungen bezahlen und die Änderungen an der Cloud-Organisation übernehmen kann.
- Globale Leser können auf eine beliebige Seite im Microsoft 365 Admin Center wechseln. Wenn Sie eine bearbeitbare Seite öffnen, wird oben eine Warnung angezeigt, die besagt, dass Sie keine Berechtigung zum Speichern von Änderungen haben, und die Schaltfläche Speichern wird deaktiviert.

Wir würden uns freuen, Ihr Feedback über die globale Leserrolle und alle rollenbasierten Berechtigungen zu erhalten, die Sie in Zukunft sehen möchten. [Feedback für rollenbasierte Berechtigungen erteilen](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/10115430-have-a-consistent-experience-when-assigning-admin)

### <a name="new-settings-page"></a>Seite "neue Einstellungen"

Das **Organisationsprofil**, die **Sicherheit & Datenschutz** und **Dienste & Add-ins-** Seiten wurden alle zu einer Seite mit drei vertikalen Registerkarten kombiniert. Und der beste Teil – von einem einzigen Standort aus können Sie nun nach allen Einstellungen suchen.
![Screen Capture: Seite "Einstellungen", wobei das Feld "alle Einstellungen Durchsuchen" oben auf der Seite markiert ist.](../media/MAC-SettingsMultiPivotSearch.png)

### <a name="training--docs"></a>Schulungs &-Dokumente

Dieser Abschnitt ist ein neues Feature in diesem Artikel, in dem wir mit der Verknüpfung zu neuer Schulung und Dokumentation beginnen, die wir für interessant halten.

Im November haben wir einige Lern Pfade zur [Microsoft Learn](https://docs.microsoft.com/learn/) -Website veröffentlicht, damit IT-Experten mehr über Microsoft 365 erfahren und geschult werden können. Check them out:

- [Microsoft 365 Grundlagen](https://docs.microsoft.com/learn/paths/m365-fundamentals/)
- [Erweitern von Office-Grundlagen](https://docs.microsoft.com/learn/paths/extend-office-fundamentals/)
- [Microsoft 365 – Modernisierung ihrer Unternehmensbereitstellung mit Windows 10-und Microsoft 365-Apps für Unternehmen](https://docs.microsoft.com/learn/paths/m365-getmodern/)
- [Verwalten Sie Ihre Unternehmensbereitstellung mit Microsoft 365](https://docs.microsoft.com/learn/paths/manage-enterprise-deployment-m365/)
- [Maßgeschneidertes Upgrade von Microsoft Office für IT](https://docs.microsoft.com/learn/paths/m365-office-for-it/)
- [Übertragen von Remotedesktops und Apps aus Azure mit Windows Virtual Desktop ](https://docs.microsoft.com/learn/paths/m365-wvd/)
- [Modernisieren Ihres Arbeitsplatzes mit Microsoft 365 und Surface for Business](https://docs.microsoft.com/learn/paths/modernize-workplace-with-m365-and-surface/)
- [Schutz von Identität und Zugriff mit Microsoft 365](https://docs.microsoft.com/learn/paths/m365-identity/)
- [Schützen von Unternehmensinformationen mit Microsoft 365](https://docs.microsoft.com/learn/paths/m365-information-protection/)
- [Verwalten der Sicherheit mit Microsoft 365](https://docs.microsoft.com/learn/paths/m365-security-management/)
- [Abwehr von Bedrohungen mit Microsoft 365 Defender](https://docs.microsoft.com/learn/paths/m365-security-threat-protection/)
- [Verwalten der Zusammenarbeit im Team mit Microsoft Teams](https://docs.microsoft.com/learn/paths/m365-manage-team-collaboration/)
- [Zusammenarbeit mithilfe von SharePoint in Microsoft 365](https://docs.microsoft.com/learn/paths/m365-teams-sharepoint/)

## <a name="october-2019---ignite-edition"></a>Oktober 2019-Ignite Edition

Willkommen bei der Ignite-Edition von What es New in the Microsoft 365 Admin Center! Dies ist natürlich keine vollständige Liste von Ankündigungen, aber hier einige Highlights. Lesen Sie auch die Ignite-Blogs, um weitere Informationen zu Releases zu erhalten:

- [Administrator-Sicherheit, Produktivität und Netzwerkverbesserungen für Microsoft 365](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/ADMIN-Security-Productivity-and-Network-Enhancements-for/ba-p/964019).
- [Neuerungen in Microsoft Teams-Ignite 2020](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-New-in-Microsoft-Teams-Ignite-2019/ba-p/937025).

### <a name="role-based-access-control"></a>Rollenbasierte Zugriffssteuerung

Es wurden viele Änderungen für Rollen im Admin Center vorgenommen, seit wir im Juni mit dem Rollout begonnen haben:

- **Rollen vergleichen** – wählen Sie bis zu 3 Rollen aus, um die Berechtigungen für jeden zu vergleichen. Auf diese Weise können Sie die am wenigsten freizügige Rolle finden, die Sie Benutzern zuweisen können. Wechseln Sie zu **Rollen**, verwenden Sie das Kontrollkästchen Mehrfachauswahl in der ersten Spalte, um bis zu drei Rollen auszuwählen, und wählen Sie dann **Rollen vergleichen** aus.

    ![Vergleichen der Rollen "Exchange-Administrator", "Helpdesk-Administrator" und "Benutzer Administrator"](../media/RBAC-CompareRoles.png)

- **Favoriten** – Sie können Ihren bevorzugten oder am häufigsten verwendeten Rollen einen Stern hinzufügen, damit Sie diese leicht finden können, indem Sie die Spalte sortieren oder einen Filter erstellen.
- **Aktive Benutzer**  >  **Rollen verwalten** – diese wurde so aktualisiert, dass Sie mit den Änderungen in den Rollen übereinstimmt. Wie bei der Rollenliste haben wir die Standardliste der Rollen auf den nützlichsten Bereich beschränkt, aber Sie können alle Rollen anzeigen, indem Sie **Alle anzeigen nach Kategorie** erweitern.
- **Globale Leserrolle** -Sie haben ihn gefragt. Du hast es! Die [globale Leser](add-users/about-admin-roles.md) Rolle!

### <a name="report-an-issue"></a>Melden eines Problems

Der Dienststatus wurde auf den neuen Stil aktualisiert, und wenn Sie von einem Problem betroffen sind, das nicht auf Ihrem Service-Integritäts Dashboard angezeigt wird, können Sie **ein Problem melden** , um es Microsoft mitzuteilen. Wechseln Sie zu **Integritäts**  >  **Dienst-Integrität**.

### <a name="viral-subscriptions"></a>"Virale" Abonnements

Wie Sie wissen, können Benutzer ﻿kostenlose Abonnements für eine Vielzahl von Produkten wie Power BI und App Connect aktivieren. Nun können Sie die "Viral Subscriptions" sehen, die Ihre Benutzer versucht haben. Wechseln Sie zu **Abrechnung**  >  **ihrer Produkte**. Wählen Sie auf der Registerkarte Abonnements den **Kontotyp** Filter aus, um die vom Benutzer erworbenen Abonnements anzuzeigen. Bei Bedarf haben Sie nun die Möglichkeit, diese Abonnements aus Ihrem Konto zu entfernen.

### <a name="user-templates"></a>Benutzervorlagen

Mithilfe von Vorlagen können Sie ganz einfach viele Benutzer hinzufügen, indem Sie die freigegebenen Einstellungen für diese Benutzer speichern und wieder verwenden. Sie können Werte für Rollen, zugewiesene Lizenzen, Kontaktinformationen, Standort und vieles mehr speichern. Wenn Sie die Vorlage verwenden, um einen neuen Benutzer zu erstellen, wird automatisch der gespeicherte Wert für diese Einstellungen abgerufen. Wechseln Sie zu **Benutzer**  >  **aktive Benutzer**, und wählen Sie dann **Benutzervorlagen** aus, um es auszuprobieren.

### <a name="office-whats-new-management-preview"></a>Office "What es New"-Verwaltung (Vorschau)

Wenn ein wichtiges Office-Feature für eine Office-App freigegeben wird, erhalten Benutzer eine "What es New"-Karte, um mehr über das neue Feature zu erfahren. Wenn Sie nicht möchten, dass Benutzer die Karte sehen, können Sie Sie ausblenden. Sie können auch auswählen, wann die Benutzer die Karte anzeigen möchten. Wechseln Sie zu **Einstellungen**  >  **Office What es New Management** , um es zu überprüfen.

### <a name="sharepoint-url-change"></a>Änderung der SharePoint-URL

Technisch gesehen ist dies nicht die Nachricht von Microsoft 365 Admin Center, aber wir sind so aufgeregt, dass Sie diese Nachricht sehen wollten:
> [!IMPORTANT]
> Sie können nun mit einer regulären URL zu Ihrem SharePoint Admin Center gelangen: [https://admin.microsoft.com/SharePoint](https://admin.microsoft.com/SharePoint)

Weitere Informationen finden Sie unter [What es New in the SharePoint Admin Center](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center).

## <a name="september-2019"></a>September 2019

Wir bieten einige aufregende Feature-Releases bei Ignite 2019 an, daher werden nur einige neue Features angekündigt, die im September veröffentlicht wurden. Bleiben Sie aber für den Artikel im nächsten Monat dran, es wird am ersten Tag von Ignite veröffentlicht!

### <a name="featured-feedback-fix--the-option-to-convert-the-deleted-users-mailbox-to-a-shared-mailbox-is-back"></a>Featured Feedback Fix – die Option, das Postfach des gelöschten Benutzers in ein freigegebenes Postfach zu konvertieren, ist zurück

Wir haben Ihr Feedback laut und deutlich gelesen, und wir haben die Möglichkeit zurückgegeben, anderen Benutzern Zugriff auf das Postfach eines gelöschten Benutzers zu gewähren, indem Sie es in ein **freigegebenes Postfach** konvertieren. Durch das Hinzufügen dieses zurück zum Assistenten zum Löschen von Benutzern können Sie entscheiden, was mit den Daten geschieht:

- E-Mail: erteilen Sie einem anderen Benutzer Zugriff auf das Postfach des gelöschten Benutzers, indem Sie es in ein freigegebenes Postfach konvertieren.
- Dateien: Speichern Sie Ihre OneDrive-Dateien, und geben Sie jemand anderen Zugriff.
- Berechtigungen: Entfernen von Berechtigungen, wenn andere Benutzer Zugriff auf dieses Postfach hatten.
- Aliase: Entfernen Sie e-Mail-Aliase, damit Sie für einen anderen Benutzer sofort verwendet werden können.
![Bildschirmaufnahme: Assistenten zum Löschen von Benutzern mit e-Mail-Aliasen, Berechtigungen, OneDrive und e-Mail-Optionen angezeigt](../media/WhatsNew-DeleteUserWiz.png)

### <a name="initial-setup"></a>Ersteinrichtung

Es wurde ein anderer unserer anfänglichen Setup-Assistenten aktualisiert: Microsoft 365 for Business. Die Schritte wurden gestrafft, und wir haben zwei der Einrichtungsaufgaben in die Setup Seite verschoben:

- **Sichere Windows 10-Computer** – Einrichten von Richtlinien zum besseren Schutz Ihrer Windows 10-Geräte vor Viren, Schadsoftware und Angriffen durch Hacker.
- **Office automatisch installieren** – Wenn Sie dies aktivieren und Benutzer ihre PCs mit Microsoft 365 Business verbunden haben, werden Ihre Computer automatisch auf die neuesten Office-Apps aktualisiert – und bleiben auf dem neuesten Stand.

## <a name="august-2019"></a>August 2019

### <a name="billing"></a>Abrechnung

Wir haben einige Updates für Abrechnung und Abonnements in diesem Monat:

- Gerätebasierte Abonnements: Sie können **Microsoft 365 apps for Education (Geräte)** Lizenzen den Geräten im Microsoft 365 Admin Center zuweisen oder aufheben. **Microsoft 365 apps for Education (Gerät)** ist eine Add-on-Lizenz, mit der Sie einem Gerät eine Lizenz zuweisen können. Wechseln Sie zu **Abrechnung**  >  **ihrer Produkte** , um die Lizenz zu finden und zu kaufen.
- Benutzerbasierte Lizenzverwaltung: Wir haben die Art und Weise aktualisiert, in der **Benutzer**  >  **aktive Benutzer** der neuen Formatvorlage Lizenzen zuweisen. Weitere Informationen finden Sie unter:
  - [Zuweisen von Lizenzen für Benutzer](manage/assign-licenses-to-users.md)
  - [Entfernen der Zuweisung von Benutzerlizenzen](manage/remove-licenses-from-users.md)

### <a name="setup-page-updates"></a>Setup Seitenaktualisierungen

Das Setup enthält jetzt Kategorien und Abschnitte, einschließlich eines **für Sie empfohlenen** Abschnitts, in dem wir Intelligent einen nächsten Schritt beim Aktivieren von Features und beim Einrichten Ihrer Organisation vorschlagen. Außerdem haben wir ein neues Feature hinzugefügt, um Folgendes einzurichten:

- **Microsoft Defender für Office 365** -Wenn Ihre Organisation für die Verwendung von Microsoft Defender für Office 365 lizenziert wurde und Sie Sie noch nicht konfiguriert oder aktiviert haben, wird diese Seite angezeigt. Wechseln Sie zu **Setup** , um es zu testen.

### <a name="report-an-issue-august"></a>Melden eines Problems (August)

Wenn Sie von einem Problem betroffen sind, das nicht auf Ihrem Service-Integritäts Dashboard angezeigt wird, bietet Ihnen das Feature **Bericht ein Problem** eine schnelle und einfache Möglichkeit, uns Bescheid zu geben. Wechseln Sie zu **Integritäts**  >  **Dienst-Integrität**.

## <a name="july-2019"></a>Juli 2019

### <a name="message-center"></a>Nachrichtencenter

Das Nachrichtencenter wurde auf das neue Design aktualisiert, und es sieht fantastisch aus!

![Bildschirmaufnahme: aktualisiertes Nachrichtencenter mit ausgewählter Registerkarte ' alle aktiven Nachrichten ' und geöffnetes Filter Menü.](../media/MAC-MessageCenterUpdated.png)

- Sie können jetzt **Nachrichten nach Status** anzeigen. Wählen Sie einfach eine der Registerkarten aus: **alle aktiven Nachrichten**, **hohe Wichtigkeit**, **Ungelesene nach** richten und **abgewiesene Nachrichten**.
- Sie können auch nach Kategoriedaten- **Datenschutz** filtern, **Änderungen planen**, **Probleme verhindern oder beheben** und **informierte** Nachrichtenkategorien bleiben.
- Wählen Sie eine Nachricht aus der Liste aus, und Sie haben einige Optionen in der Befehlsleiste: **verwerfen**, **als gelesen markieren** oder **als ungelesen** markieren oder **Freigeben**.
- Wenn Sie eine Nachricht öffnen, haben Sie noch weitere Optionen:
  - Kopieren Sie einen Link der Nachricht in Ihre Zwischenablage, um ihn später zu speichern oder um ihn für Kollegen freizugeben.
  - Nachrichten als **gelesen** oder **Ungelesen** markieren.
  - Geben Sie Feedback zu einer Nachricht durch Auswählen von **like** oder **dislike** wird ein Feedback Bereich geöffnet, in dem Sie aufgefordert werden, ein bestimmtes Feedback zu den Informationen zu erhalten, die Ihnen bei dieser Nachricht gefallen oder nicht gefällt haben.

### <a name="navigation-pane-intelligence"></a>Intelligence für den Navigationsbereich

 Der Navigationsbereich merkt sich nun ihre letzten Aktionen und zeigt den Bereich im letzten Zustand an, in dem Sie ihn hinterlassen haben. Außerdem werden häufig verwendete Elemente standardmäßig sichtbar gemacht.

### <a name="initial-setup--the-setup-page"></a>Erst Setup & der Seite "Setup"

Wir haben einige interessante Änderungen, die Ihnen helfen, Ihre Organisation einzurichten. Lassen Sie uns zunächst den Unterschied zwischen **Setup** und **Setup Seite** besprechen. **Setup** bezieht sich auf den anfänglichen Setup-Assistenten, den Sie für die Onlinedienste von Microsoft an Bord verwendet haben. Dies umfasst normalerweise drei spezifische Schritte: **Verbinden einer Domäne**, **Hinzufügen von Benutzern** und **herunterladen der Office-Apps**. Die Seite **Setup** ist die Seite im Admin Center, die die Einrichtung von Aufgaben empfohlen hat, um sicherzustellen, dass Sie Ihre Abonnements optimal nutzen – wie das Aktivieren von Features, für die Sie Lizenzen erworben haben.

- **Setup** – der anfängliche Setup-Assistent wurde für **Microsoft 365 for Business** -Abonnements aktualisiert. Dieses neue Design hilft neuen Organisationen, den Assistenten schneller und mit größerer erfolgreiche durch zugewinnen.
- **Seite "Setup** " – die **Setup** Seite unterstützt Sie beim Abschließen der Einrichtung und Sicherung der Dienste, die mit ihren Abonnements geliefert werden. Auf der Seite **Setup** werden auch alle abgewiesenen Empfehlungen angezeigt. Um zu sehen, ob Sie noch für Ihre Abonnements verfügbar ist, wechseln Sie zum **Microsoft 365 Admin Center**-  >  **Setup**.

### <a name="billing--subscriptions"></a>Abrechnungs & Abonnements

- **Software** Produkttyp – Sie können jetzt Softwareprodukte anzeigen, die über einen Anbieter von Cloud-Diensten (Service Provider, CSP) erworben wurden. Um Ihre Downloads und Schlüssel anzuzeigen, wechseln Sie zur  >    >  Registerkarte Abrechnungs **Software** für Produkte.
- Sie können moderne Azure-Produkte und-Dienste im Microsoft 365 Admin Center anzeigen, unabhängig davon, ob Sie Sie von Microsoft oder einem Drittanbieter erworben haben. Beispiele für moderne Azure-Produkte enthalten:
  - Azure reservierte virtuelle Instanzen
  - Azure-Support Pläne
  - Azure Hybrid use Benefits (AHUB)
  - Verwalten von Anwendungen
  - Geräte Dienste
  - Azure-Abonnements

### <a name="simplify-multi-factor-authentication"></a>Vereinfachung der mehrstufigen Authentifizierung

Administratoren haben Zugriff auf vertrauliche Informationen in Ihrer Organisation. Erfordern, dass alle Administratoren bei der Anmeldung mehrstufige Authentifizierung verwenden. Der neue Assistent hilft Ihnen, es mit nur einem Schritt zu erledigen. Um es auszuprobieren, gehen Sie zu **Setup**  >  **verstärken der Anmeldungssicherheit**.

### <a name="users"></a>Benutzer

Die Seiten " **Gelöschte Benutzer** " und " **Gastbenutzer** " wurden auf die neue Formatvorlage aktualisiert.

- **Gastbenutzer**: Sie fügen Gastbenutzer hinzu, indem Sie Sie zum Anzeigen oder Freigeben von Dateien aus SharePoint oder OneDrive einladen. Sie können Gastbenutzer von Gastbenutzern von **Benutzern** anzeigen  >  .
- **Gelöschte Benutzer**: auf der Seite aktualisierte **Gelöschte Benutzer** können Sie alle Aktionen ausführen, die Sie im älteren Admin Center durchführen konnten, jetzt jedoch Spalten hinzufügen und entfernen. Und wir haben viele Spaltenoptionen zur Auswahl. Tatsächlich sind es die gleichen Spalten, die Sie auf der Seite " **aktive Benutzer** " auswählen können.

## <a name="june-2019"></a>Juni 2019

### <a name="featured-feedback-request---dark-mode"></a>Empfohlene Feedbackanforderung – dunkler Modus

Das Anzeigen des Admin Centers im dunklen Modus erfolgt in der Vorschau! Sie können es auf der **Start** Seite erst jetzt testen. Auf der **Start** Seite befindet sich die Schaltfläche **dunkler Modus** in der Befehlsleiste neben dem Link **Neuerungen** .

### <a name="roles-management"></a>Rollenverwaltung

Ende Juni begannen wir mit der Einführung neuer Methoden zum Verwalten von Administratorrollen. Wenn es für Sie verfügbar ist, wechseln Sie zu **Rollen**  >  **Rollen**. Bis dahin werfen Sie einen Blick-IT es awesome!
<br> ![Bildschirmaufnahme: Administratorrollen Liste mit hervorgehobenem Detailbereich für Benutzer-admin-Rollen.](../media/MAC-AdminRoles-Featured.png) <br>

Dank dieser neuen Benutzeroberfläche können Sie einfacher erkennen, wer Administratorberechtigungen hat, und Rollen zuweisen, die Ihren Administratoren die richtige Zugriffsebene gewähren. Außerdem wurden von Azure AD weitere Rollen hinzugefügt, sodass Sie keine Zeit verschwenden, an mehreren Verwaltungszentren teilhaben zu müssen.
Was können Sie sonst noch tun?

- Exportieren Sie eine Liste aller Administratoren in Ihrer Organisation, denen Azure Active Directory Rollen in Microsoft 365 zugewiesen sind.  
- Anzeigen aller Administratoren, die einer bestimmten Rolle zugewiesen sind, hinzufügen oder Entfernen von Administratoren aus einer bestimmten Rolle, suchen nach Rollen nach Name und Stichwort und weitere Informationen dazu, was die einzelnen Rollen Benutzern ermöglichen.
- Schnelles Suchen nach einer bestimmten Rolle und Erstellen von Filtern

### <a name="payment-method"></a>Zahlungsmethode

Wir haben die Art und Weise aktualisiert, wie Sie Ihre Abonnements bezahlen. Wechseln Sie zu **Billing**  >  **Bills &** Payments  >  **Payment Methods**. Sie können Ihre Zahlungsmethoden in einer Listenansicht anzeigen. Wählen Sie ein beliebiges Element in der Liste aus, um es zu entfernen, zu bearbeiten und einfach zu sehen, welchem Abonnement die Zahlungsmethode zugeordnet ist.

## <a name="may-2019"></a>Mai 2019

### <a name="mays-featured-fix---case-sensitivity"></a>Mai es Featured Fix-Case-Empfindlichkeit

Wenn Sie nun nach freigegebenen Postfächern, Kontakten, Ressourcen und Postfachberechtigungen suchen, müssen bei Ihren Suchbegriffen die Groß-/Kleinschreibung nicht beachtet werden.

**Benutzer-und Gruppenverwaltung** In diesem Monat haben wir " **Benutzer blockieren**", " **Kennwort zurücksetzen**", " **Kontakt** Listenansicht", " **Gruppen** -Listenansicht" und " **Gruppen** Detailseiten" auf den neuen Admin Center-Stil aktualisiert.

- In der Listenansicht neue **Gruppen** erhalten Sie umfassendere Daten zu ihren Gruppen, und Sie können die Art und Weise, wie Sie Ihre Daten sehen, anpassen, und die Gruppenliste merkt sich, wie die Daten angezeigt werden sollen. Beispielsweise können Sie jetzt nach **Gruppen mit Teams** filtern, um festzustellen, ob Ihre Gruppen Teil eines Teams sind, und Sie können die Spalte **Status des Teams** hinzufügen.
- In der Liste "Gruppen" werden außerdem alle Verbesserungen an der Listen Erfahrung in der Benutzerverwaltung, einschließlich schnell Aktionen und der kontextbezogenen Befehlsleiste, vorgenommen.

**Empfehlungen**<br>
Möglicherweise wird in Ihrem Admin Center ein neues Empfehlungs Popup angezeigt – wir haben soeben 4 neue hinzugefügt. Selbstverständlich werden nur Empfehlungen angezeigt, wenn wir davon ausgehen, dass Ihre Organisation davon profitiert. Aber warten Sie nicht, bis wir Ihnen die Empfehlung zeigen-Sie können Sie aus der Kartenbibliothek hinzufügen.

- **Kennwortablauf** – es wird empfohlen, dass Kennwörter auf " **nie ablaufen**" festgelegt werden. Wenn Ihre Organisation eine andere Einstellung hat, wird diese Empfehlung möglicherweise nur angezeigt.
- **Zu viele globale Administratoren** – da es sich bei den zu vielen globalen Administratoren um eine Sicherheitsbedrohung handelt, wenn Sie über mehr als 4 globale Administratoren verfügen, wird diese Empfehlung angezeigt. Wir empfehlen Benutzern nur den Zugriff zu gewähren, den Sie benötigen, um Ihre Arbeit zu erledigen.
- **InTune-Geräteschutz** : Wenn Ihre Lizenzen InTune enthalten und wir feststellen, dass Sie die Einrichtung von InTune oder Ihre Geräte nicht abgeschlossen haben, wird empfohlen, dass Sie eine InTune-Richtlinie erstellen, um die Dateien Ihrer Organisation zu schützen, wenn Benutzer von ihren mobilen Geräten aus darauf zugreifen.
- **Monatliche Office-Feature-Updates** – wir haben Feedback von unseren sehr kleinen Kunden bekommen, dass Ihre Benutzer, wenn Sie monatliche Office-Feature-Updates erhalten, glücklicher sind. Wenn Sie also ein sehr kleines Unternehmen sind und Ihre Office-Feature-Updates derzeit alle sechs Monate erhalten, wird diese Empfehlung angezeigt.

**Einstellungen** <br>
Was die Einstellungen anbetrifft, gibt es einige Änderungen. Meistens aktualisieren Sie einfach die vorhandenen Einstellungen auf den neuen Admin Center-Stil. Wenn wir fortfahren und neue Einstellungen hinzufügen, die Sie noch nie zuvor gesehen haben, werden wir Sie hier ansprechen. Und wir haben eine vollständige Einstellung, die Sie ankündigen müssen: **moderne Authentifizierung**. Ja, es gibt eine neue Einstellung zum Aktivieren der **modernen Authentifizierung**! Zum Auschecken wechseln Sie zu **Einstellungen**  >  **Dienste & Add-ins**  >  **moderne Authentifizierung**.

## <a name="april-2019"></a>April 2019

Die Dinge sehen für das Admin Center gut aus. Wir haben Ihr Feedback und ihre Vorschläge gelesen und die meisten davon beantwortet, und Sie sollten wirklich alles Unternehmen, was Sie zu Herzen sagen müssen. Selbstverständlich arbeiten wir immer noch daran, sicherzustellen, dass alles auf die Parität mit dem alten Admin Center ausgerichtet ist. Denken Sie daran, dass Sie bei der Einführung neuer Features möglicherweise nicht sofort darauf gelangen.

### <a name="featured-feature---add-users"></a>Featured Feature – hinzufügen von Benutzern

Für April haben wir den Assistenten zum **Hinzufügen von Benutzern** , der Sie durchläuft... warten Sie... Hinzufügen von Benutzern. Es ist ein Schritt-für-Schritt, um die grundlegenden Informationen des Benutzers wie e-Mail und Anzeigenamen hinzuzufügen, eine Lizenz und eine Rolle zuzuweisen, Ihre Kontaktinformationen hinzuzufügen und dann das Konto des Benutzers zu überprüfen, bevor Sie einen Commit ausführen. **Warum haben wir diese Änderung vorgenommen?** Wir haben Ihr Feedback gehört, dass Sie den fast unendlichen Bildlauf nicht gemocht haben, um Benutzer in der vorherigen Umgebung hinzuzufügen.
<br> ![Bildschirmausschnitt des Assistenten zum Hinzufügen von Benutzern.](../media/MAC-AddUserWizard.png) <br>

Es gibt zwei Möglichkeiten, Sie zu überprüfen: <br>

1. Wählen Sie auf der **Start** Seite Benutzer aus der **Benutzer Verwaltungs** Karte **Hinzufügen** aus. Der Assistent wird direkt dort geöffnet, sodass Sie nicht von jeder Arbeit auf der **Start** Seite aus navigieren müssen.
2. Wechseln Sie zu **Benutzer**  >  **aktive Benutzer**, und wählen Sie dann in der Befehlsleiste **Benutzer hinzufügen** aus.
<br><br>

Wir haben einige weitere Änderungen an der **Benutzerverwaltung** vorgenommen, hier eine kurze Liste:

- Der Bereich " **Rollen verwalten** " wurde auf die neue Formatvorlage aktualisiert und ist zugänglich. Außerdem haben wir die Bereiche **Block User** und **Delete User** auf die neue Formatvorlage aktualisiert.
- **Verwalten von Produktlizenzen** geänderte Position in der Befehlsleiste.
- Das Ändern des Fotos eines Benutzers ist jetzt einfacher. Wählen Sie in **aktive Benutzer** einen Benutzer aus, und ändern Sie dann das **Foto** unter dem Bild.

### <a name="but-wait-theres-more"></a>Aber warten Sie! Es gibt noch mehr

- Es gibt ein neues Setup-Banner auf der **Start** Seite, das Sie sehen, wenn Sie die Schritte zum Einrichten, wie das Hinzufügen einer Domäne, das Hinzufügen von Benutzern und das Herunterladen der Office-Apps noch nicht abgeschlossen haben.
- Der **Gruppen** Listen-und Detailbereich wurde auf die neue Formatvorlage aktualisiert. Wechseln Sie zu **Gruppen**  >  **Gruppen** , um die Änderungen anzuzeigen.
  - Apropos Gruppen: Wir haben auch eine **Microsoft Teams** -Registerkarte zum Gruppen Detailbereich hinzugefügt, in dem Sie jede Microsoft 365-Gruppe in ein Team umwandeln können. Um "teamify" eine Gruppe auszuwählen, wählen Sie in der Liste eine beliebige Microsoft 365-Gruppe aus, wählen Sie die Registerkarte **Microsoft Teams** aus, und erstellen Sie dann **Team**. Wenn es sich bei der Gruppe bereits um ein Team handelt, erhalten Sie einen Link, um Sie über das **Teams Admin Center** zu verwalten.
  - Schließlich können Sie den Status " **Teams** " zur Liste " **Gruppen** " hinzufügen. Wählen Sie in der Spalte Kopfzeile die Option **Spalten**  >  **Teams-Status**  >  **Speichern** aus.
- **Neue beschränkte Administratorrollen** – wir veröffentlichen einige neue Administratorrollen, sodass Sie Benutzern nur den Zugriff gewähren können, den Sie benötigen.
  - **Kaizala-Administrator**: Benutzer in dieser Rolle verfügen über die Berechtigung zum Ausführen aller Verwaltungsaufgaben in Microsoft Kaizala, einschließlich Erstellen und Verwalten von Benutzern im Verzeichnis Kaizala, Verwalten von Kaizala Gruppen, Verwalten von Aktionskarten und Connectors und Erstellen von Dienstanforderungen.
  - **Search admin**: Benutzer in dieser Rolle haben Vollzugriff auf alle Microsoft Search Management-Funktionen im Microsoft 365 Admin Center. Suchadministratoren können die Rollen "Such-admin" und "Such-Editor" an Benutzer delegieren und Inhalte wie Lesezeichen, Q&A-Elemente und-Speicherorte erstellen und verwalten. Darüber hinaus können diese Benutzer das Nachrichtencenter anzeigen, den Dienststatus überwachen und Dienstanforderungen erstellen.
  - **Such-Editor**: Benutzer in dieser Rolle können Inhalte für die Microsoft-Suche im Microsoft 365 Admin Center erstellen, verwalten und löschen, einschließlich Lesezeichen, Q&A-Elementen und-Speicherorte.
- In diesem Monat gibt es eine Goldgrube an **Abrechnungs** Änderungen...
  - Sie können jetzt die CVV für vorhandene Kreditkarten aktualisieren, ohne Sie löschen und erneut hinzufügen zu müssen. Sie können die CVV aktualisieren, indem Sie auf  >  **Zahlungsmethoden** für Zahlungen wechseln.
    - Wir haben es einfacher gemacht, Ihre **Rechnungen** zu finden und alle Abrechnungsprobleme zu verstehen, die Ihr Konto haben kann. Nun können Sie Ihre Rechnungen im Webbrowser anzeigen, anstatt die PDF herunterladen zu müssen. Wechseln Sie zu **Rechnungen**  >  **Rechnungen**.
    - Auf der Seite **Ihre Produkte** werden jetzt die Abonnementinformationen aggregiert, wenn Sie mehrere Abonnements desselben Typs haben.

## <a name="march-2019---weve-officially-released-the-admin-center"></a>März 2019 – wir haben das Admin Center offiziell veröffentlicht.

Nun, wenn Sie die aufregenden Neuigkeiten verpasst haben, veröffentlichen wir offiziell das neue und verbesserte Microsoft 365 Admin Center! Hier ist der Blogbeitrag, in dem wir es angekündigt haben: [das neue Microsoft 365 Admin Center, das heute verfügbar](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/The-new-Microsoft-365-admin-center-available-today/ba-p/377870)ist. Für März verlassen wir uns auf den Blogbeitrag für Sie, um die Features veröffentlicht-Plus, können Sie auch den Beitrag für die Funktionen, die in naher Zukunft veröffentlicht werden, was wir nicht in Kerninhalten tun dürfen, zu lesen.
<br> ![Bildschirmaufnahme der Startseite des Microsoft 365 Admin Center.](../media/M365AC-HomePage.png) <br>
Wir haben eine Änderung am Bereich **Abrechnungs & Abonnements** , den wir erwähnen möchten. Ich meine, Ihr habt nicht gedacht, dass wir mit der Verbesserung fertig sind, oder? Weil wir es nicht sind! In diesem Monat haben wir hinzugefügt, dass Sie Ihre Partnerbeziehungen mit **Abrechnungs**  >  **Konten** verwalten können. Von hier aus können Sie Ihre Partnerbeziehungen über Berater, CSP und indirekte Händler hinweg überprüfen. Sie können auch neue Partner Beziehungs Anforderungen akzeptieren, einschließlich Delegierter Administratorberechtigungen.

Ihr Feedback ist wie immer wichtig für uns, also halten Sie es auf dem neuesten Stand. Auf einer beliebigen Seite im Admin Center können Sie Feedback geben, indem Sie unten rechts **Feedback geben** auswählen, neben **benötigen Sie Hilfe?**

## <a name="february-2019---billing--subscriptions-edition"></a>Februar 2019-Abrechnung & Subscriptions-Edition

In diesem Monat konzentrieren wir uns auf alle Verbesserungen, die wir an den Bereichen vorgenommen haben, die liebevoll als "Abrechnung und Abonnements" bezeichnet werden. In der Vergangenheit haben Sie sich wahrscheinlich nicht auf diese Dinge liebevoll berufen, aber wir denken, dass Sie es jetzt tun werden...

- **Zahlungsmethoden** – wir haben Ihr Feedback gehört, dass die Aktualisierung Ihrer Zahlungsmethode schwierig war, und wir haben viele Änderungen daran vorgenommen. Wechseln Sie zu **Abrechnungs**  >  **Zahlungsmethoden**. Sie können Ihre Zahlungsmethoden wie Ihre Visa-Karte und das Abonnement, mit dem Sie verbunden sind, ganz einfach sehen. Wählen Sie in der Liste mit den Zahlungsmethoden das Menü **mehr** (3 kleine Punkte neben dem Ablaufdatum) aus, und wählen Sie dann **Abonnements anzeigen** aus. Sie können Ihre Zahlungsmethoden auch über das Menü **Weitere** bearbeiten und löschen.
- **Abrechnungskonto** – gezielte Release-Kunden sehen zuerst die neue Abrechnungskonto Seite und dann werden wir Sie auf der ganzen Welt Ausrollen. Wenn es für Sie verfügbar ist, wechseln Sie zu **Abrechnungs**  >  **Konto**. Was können Sie auf der Seite "neues Abrechnungskonto" tun? Ich bin froh, dass Sie gefragt haben:
  - Aktualisieren Sie die Adresse und andere Kontaktinformationen in Ihrem Organisationsprofil direkt auf dieser Seite. Sie müssen nicht zum Organisationsprofil " **Einstellungen**" wechseln  >  , es sei denn, Sie möchten.
  - Und wir machen das Leben für Kunden mit direkter oder Volumenlizenzierung einfacher, Sie können Kundenverträge von **Abrechnungskonten** akzeptieren und überprüfen. Sie können auch eine Verbindung mit anderen Organisationen herstellen, sodass Sie die Organisationen miteinander verknüpfen können, um Lizenzen und Ressourcen freizugeben.
- Wir haben auch einige kleinere Verbesserungen und Bugfixes gemacht:
  - Reaktivieren eines Abonnements mit einer Rechnungszahlung
  - Bearbeiten der Dienstnutzungsadresse für Ihre Abonnements
  - Auf der Seite Inventar Details haben wir einige Benachrichtigungs Verbesserungen hinzugefügt, wir verknüpfen Sie mit der tatsächlichen Seite, auf der Sie die Arbeit ausführen können, und es gibt weitere Aktionen auf der Inventory-Detailkarte. Wechseln Sie zu **Fakturierungs**  >  **Rechnungen**, um  >  **Details** zu jeder Rechnung anzuzeigen.

## <a name="january-2019---happy-new-year"></a>Januar 2019-Happy New Year

- Hinzufügen von **Diensten &-Add-ins** – wir haben weitere **Einstellungen > Dienste & Add-ins** -Seiten aktualisiert. Testen Sie die integrierten Apps oder Berichte, um die neuesten.
- **Suchen Sie nach Verbesserungen?** Suchen Sie nicht weiter als das **Suchfeld** in der Befehlsleiste. Es wurde aktualisiert, damit Sie nach Aufgaben suchen können. Versuchen Sie beispielsweise "Kennwortzurücksetzung" oder "Benutzer hinzufügen".

### <a name="featured-feedback-fix---licenses-and-apps"></a>Featured Feedback Fix – Lizenzen und Apps

Wir haben **Lizenzen und apps** im Benutzerdetail Bereich basierend auf Ihrem Feedback erneut kombiniert. Zunächst trennten wir die beiden Features, um Platz für die Details aller Lizenz-und App-Möglichkeiten bereitzustellen. Wir haben von Ihnen gehört, dass durch das Trennen von Lizenzen und apps in zwei Bereiche Verwirrung gefügt wurde. Wir haben zugehört und Lizenzen und apps in einem Tab wieder zusammengeführt. Jetzt können Sie sicherstellen, dass eine app in allen Lizenzen deaktiviert ist, die einem Benutzer in einem Bereich zugewiesen sind. Milch und Cookies. Lizenzen und apps. Wir erhalten Sie jetzt.

Check it out: **Benutzer > aktive Benutzer >** **Benutzer > Lizenzen und apps bearbeiten oder hinzufügen**
