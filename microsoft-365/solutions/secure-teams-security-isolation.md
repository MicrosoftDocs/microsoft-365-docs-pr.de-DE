---
title: Konfigurieren eines Teams mit Sicherheitsisolierung
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Hier erfahren Sie, wie Sie ein Team mit einer eindeutigen Vertraulichkeitsbezeichnung für Sicherheit erstellen.
ms.openlocfilehash: b16133a02c82c2b2ab0e56a5545e19b160933664
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560231"
---
# <a name="configure-a-team-with-security-isolation"></a>Konfigurieren eines Teams mit Sicherheitsisolierung

In diesem Artikel finden Sie Empfehlungen und Schritte zum Konfigurieren eines privaten Teams in Microsoft Teams und zum Verwenden einer eindeutigen Vertraulichkeitsbezeichnung zum Verschlüsseln von Dateien, sodass nur Teammitglieder Sie entschlüsseln können.

Neben dem privaten Zugriff wird in diesem Artikel beschrieben, wie die zugehörige SharePoint-Website, auf die Sie über den Abschnitt **Dateien** eines Teamkanals zugreifen können, für die zusätzliche Sicherheit konfiguriert wird, die für die Speicherung von streng regulierten Daten erforderlich ist.

Die Elemente der Konfiguration für ein Team für streng regulierte Daten sind:

- Ein privates Team
- Zusätzliche Sicherheit auf der zugehörigen SharePoint-Website für das Team, die verhindert,
  - Dass Mitglieder der Website die Website für andere Personen freigeben.
  - Dass Nicht-Mitglieder der Website Zugriff auf die Website anfordern.
- Eine Vertraulichkeitsbezeichnung speziell für dieses Team, die:
    - den Zugriff auf SharePoint-Inhalte von nicht verwalteten Geräten verhindert
    - dem Gast den Zugang zum Team erlaubt oder verweigert, je nach Ihren Anforderungen
    - Dokumente verschlüsselt, auf die das Etikett angewendet wird

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie die [Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Office 365-Gruppen und SharePoint-Websites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) aktiviert haben, bevor Sie mit den Schritten in diesem Artikel fortfahren.

<a name="poster"></a> Eine zweiseitige Zusammenfassung dieses Szenarios zeigt das [Poster „Microsoft-Team mit Sicherheitsisolierung“](../downloads/team-security-isolation-poster.pdf).

[![Poster „Microsoft-Team mit Sicherheitsisolierung“](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)

Sie können dieses Poster auch im [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf)- oder [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pptx)-Format herunterladen und in den Formaten "Brief", "Legal" oder "Tabloid" (27,94 x 43,18 cm) ausdrucken.

## <a name="initial-protections"></a>Erste Schutzmaßnahmen

Wenn Sie den Zugriff auf das Team und die zugrunde liegende SharePoint-Website schützen möchten, überprüfen Sie die folgenden bewährten Methoden:
- [Identitäts- und Gerätezugriffsrichtlinien](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies)
- [SharePoint-Zugriffsrichtlinien](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).
- [Bereitstellen von Teams mit grundlegendem Schutz](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a>Gastfreigabe

Je nach Art des Unternehmens ist möglicherweise die Gastfreigabe für dieses Team erforderlich. Wenn Sie die Zusammenarbeit mit Personen außerhalb Ihrer Organisation in einem solchen Team planen, aktivieren Sie die Gastfreigabe. 

Details zur sicheren Freigabe für Gäste finden Sie in den folgenden Ressourcen:

- [Begrenzen der versehentlichen Gefährdung von Dateien bei der Freigabe für Personen außerhalb Ihrer Organisation](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [Erstellen einer sicheren Gastfreigabeumgebung](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

Für das Zulassen oder Blockieren des Gastfreigabe verwenden wir eine Kombination aus einer Vertraulichkeitsbezeichnung für das Team und Steuerelementen für die Freigabe auf Team- und Websiteebene für die zugeordnete SharePoint-Website, die beide später behandelt werden.

## <a name="create-a-private-team"></a>Erstellen eines privaten Teams

Da wir eine Vertraulichkeitsbezeichnung speziell für dieses Team erstellen, besteht der nächste Schritt darin, das Team zu erstellen. Wenn Sie über ein vorhandenes Team verfügen, können Sie es verwenden.

So erstellen Sie ein Team für vertrauliche Informationen
1. Klicken Sie in Microsoft Teams auf der linken Seite auf **Teams** und dann unten in der Teamliste auf **Einem Team beitreten oder ein Team erstellen**.
2. Klicken Sie auf **Team erstellen** (erste Karte, obere linke Ecke).
3. Wählen Sie **Neuerstellen eines Teams**.
4. Behalten Sie in der Liste **Vertraulichkeit** die Standardeinstellung bei.
5. Klicken Sie unter **Datenschutz** auf **Privat**.
6. Geben Sie einen Namen für das Team ein, der sich auf Ihr sensibles Projekt bezieht. Z. B. **Projekt Saturn**.
7. Klicken Sie auf **Erstellen**.
8. Fügen Sie Benutzer zu dem Team hinzu, und klicken Sie dann auf **Schließen**.

## <a name="private-channel-settings"></a>Einstellungen für private Kanäle

Es wird empfohlen, die Erstellung privater Kanäle für Teambesitzer zu beschränken.

So schränken Sie die Erstellung privater Kanäle ein
1. Klicken Sie im Team auf **Weitere Optionen** und dann auf **Team verwalten**.
2. Erweitern Sie auf der Registerkarte **Einstellungen** den Eintrag **Mitgliedsberechtigungen**.
3. Deaktivieren Sie das Kontrollkästchen **Mitglieder können private Kanäle erstellen**.

Sie können auch [Teams-Richtlinien](https://docs.microsoft.com/MicrosoftTeams/teams-policies) verwenden, um zu steuern, wer private Kanäle erstellen kann.

## <a name="create-a-sensitivity-label"></a>Erstellen einer Vertraulichkeitsbezeichnung

Wenn Sie ein Team für die Sicherheitsisolierung konfigurieren möchten, verwenden wir eine speziell für dieses Team erstellte Vertraulichkeitsbezeichnung. Diese Bezeichnung wird auf Teamebene verwendet, um die gemeinsame Nutzung von Gästen zu steuern und den Zugriff von nicht verwalteten Geräten zu blockieren. Sie kann auch dazu verwendet werden, einzelne Dateien im Team zu klassifizieren und zu verschlüsseln, sodass sie nur von Teambesitzern und Mitgliedern geöffnet werden können.

Wenn Sie über einen internen Partner oder eine Gruppe von Interessengruppen verfügen, die in der Lage sein sollen, verschlüsselte Dokumente anzuzeigen, diese jedoch nicht zu bearbeiten, können Sie sie zur Bezeichnung mit der Berechtigung „Nur Anzeigen“ hinzufügen. Sie können diese Personen dann der SharePoint-Website des Teams mit Leseberechtigungen hinzufügen, und sie haben schreibgeschützten Zugriff auf die Website, auf der die Dokumente aufbewahrt werden, aber nicht auf das Team selbst.

Erstellen einer Vertraulichkeitsbezeichnung
1. Öffnen Sie das [Microsoft 365 Compliance Center](https://compliance.microsoft.com).
2. Klicken Sie unter **Lösungen**auf **Informationsschutz**.
3. Klicken Sie auf **Bezeichnung erstellen**.
4. Geben Sie einen Namen für die Bezeichnung ein, der dem Namen Ihres Teams ähnelt. Z. b. **Streng vertraulich –⁠ Projekt Saturn**.
5. Fügen Sie eine QuickInfo hinzu, und klicken Sie dann auf **Weiter**.
6. Wählen Sie auf der Seite **Verschlüsselung** im Dropdownmenü **Verschlüsselung** **Anwenden**aus.
7. Hinzufügen der Team-Berechtigungen:<br>
  a. Klicken Sie auf **Zuweisen von Berechtigungen**.<br>
  b. Klicken Sie auf **Benutzergruppen hinzufügen**, wählen Sie das von Ihnen erstellte Team aus und klicken Sie dann auf **Hinzufügen**.<br>
  c. Klicken Sie auf **Berechtigungen auswählen**.<br>
  d. Wählen Sie in der Dropdownliste **Mitautor**, und klicken Sie dann auf **Speichern**.<br>
8. Wenn Sie Benutzer oder Gruppen mit schreibgeschütztem Zugriff auf Dateien mit dieser Bezeichnung einbeziehen möchten:<br>
  a. Klicken Sie auf **Zuweisen von Berechtigungen**.<br>
  b. Klicken Sie auf **Benutzergruppen hinzufügen**, wählen Sie die Benutzer oder die Gruppen, die Sie hinzufügen möchten, aus und klicken Sie dann auf **Hinzufügen**.<br>
  c. Klicken Sie auf **Berechtigungen auswählen**.<br>
  d. Wählen Sie in der Dropdownliste **Nur lesen**, und klicken Sie dann auf **Speichern**.<br>
  e. Klicken Sie auf **Speichern**.
9. Klicken Sie auf **Weiter**.
10. Aktivieren Sie auf der Seite **Inhaltskennzeichnung** die Inhaltskennzeichnung, wenn Dateien, die mit dieser Bezeichnung klassifiziert wurden, automatisch eine Kopf-oder Fußzeile oder ein Wasserzeichen hinzugefügt werden soll.
11. Legen Sie auf der Seite **Website- und Gruppeneinstellungen** die Option **Website- und Gruppeneinstellungen** auf **Ein** fest.
12. Wählen Sie in der Dropdownliste **Datenschutz für mit Office 365-Gruppen verbundene Teamwebsites** die Option **Privat – nur Mitglieder können auf die Website zugreifen** aus.
13. Wenn Sie den Gastzugriff zulassen möchten, aktivieren Sie **Office 365-Gruppenbesitzer dürfen Personen außerhalb der Organisation zur Gruppe hinzufügen**. 
14. Wählen Sie unter **Nicht verwaltete Geräte** die Option **Zugriff blockieren**.
15. Klicken Sie auf **Weiter**.
16. Klicken Sie auf der Seite **Automatisches Bezeichnen für Office-Apps** auf **Weiter**.
17. Klicken Sie auf **Absenden** und anschließend auf **Fertig**.

Nachdem Sie die Bezeichnung erstellt haben, müssen Sie sie für die Benutzer veröffentlichen, die sie verwenden sollen. In diesem Fall wird die Bezeichnung nur für Personen im Team verfügbar sein.

So veröffentlichen Sie eine Vertraulichkeitsbezeichnung
1. Wählen Sie im Microsoft 365 Compliance Center auf der Seite **Informationsschutz** die Registerkarte **Bezeichnungsrichtlinien**.
2. Klicken Sie auf **Bezeichnungen veröffentlichen**.
3. Klicken Sie auf der Seite **Zu veröffentlichende Vertraulichkeitsbezeichnungen wählen** auf **Zu veröffentlichende Vertraulichkeitsbezeichnungen wählen**.
4. Wählen Sie die von Ihnen erstellten Bezeichnungen aus, und klicken Sie dann auf **Hinzufügen**.
5. Klicken Sie auf **Weiter**.
6. Klicken Sie auf der Seite „Für Benutzer und Gruppen veröffentlichen“ auf **Benutzer und Gruppen auswählen**.
7. Klicken Sie auf **Hinzufügen** und wählen Sie dann das von Ihnen erstellte Team aus.
8. Klicken Sie auf **Hinzufügen** und dann auf **Fertig**.
9. Klicken Sie auf **Weiter**.
10. Aktivieren Sie auf der Seite Richtlinieneinstellungen das Kontrollkästchen **Benutzer müssen eine Begründung für das Entfernen einer Bezeichnung oder einer Bezeichnung mit niedrigerer Klassifizierung angeben**, und klicken Sie dann auf **Weiter**.
11. Geben Sie einen Namen für die Richtlinie ein und klicken Sie dann auf **Weiter**.
12. Klicken Sie auf **Absenden** und dann auf **Fertig**.

## <a name="apply-the-label-to-the-team"></a>Anwenden der Bezeichnung auf das Team

Nachdem die Bezeichnung veröffentlicht wurde, müssen Sie sie auf das Team anwenden, damit die Einstellungen für Gastfreigabe und verwaltete Geräte wirksam werden. Das kann im SharePoint Online Admin Center erledigt werden. Beachten Sie, dass es einige Zeit dauern kann, bis die Bezeichnung nach ihrer Veröffentlichung verfügbar ist.

So wenden Sie die Vertraulichkeitsbezeichnung an
1. Öffnen Sie das [SharePoint Online Admin Center](https://admin.microsoft.com/sharepoint).
2. Klicken Sie unter **Websites** auf **Aktive Websites**.
3. Klicken Sie auf die dem Team zugeordnete Website.
4. Klicken Sie auf der Registerkarte **Richtlinien** unter **Vertraulichkeit** auf **Bearbeiten**.
5. Wählen Sie die von Ihnen erstellten Bezeichnungen aus, und klicken Sie dann auf **Speichern**.

## <a name="sharepoint-settings"></a>SharePoint-Einstellungen

In SharePoint müssen Sie drei Schritte ausführen:

- Aktualisieren Sie die Gastfreigabeeinstellungen für die Website im SharePoint Online Admin Center so, dass sie jenen entsprechen, die Sie beim Erstellen der Bezeichnung vorgenommen haben, und legen Sie für den standardmäßigen Freigabelink *Personen mit vorhandenem Zugriff* fest.
- Aktualisieren Sie die Website-Freigabeeinstellungen auf der Website selbst, um zu verhindern, dass Mitglieder Dateien, Ordner oder die Website freigeben, und Zugriffsanforderungen ausschalten.
- Wenn Sie Personen oder Gruppen zur Bezeichnung mit Nur-Leseberechtigungen hinzugefügt haben, können Sie sie mit Leseberechtigungen zur SharePoint-Website hinzufügen.

### <a name="sharepoint-guest-settings"></a>SharePoint-Gasteinstellungen

Die Einstellung für die Gastfreigabe, die Sie beim Erstellen der Bezeichnung ausgewählt haben (die sich nur auf die Teammitgliedschaft auswirkt), sollten mit den Gast-Freigabeeinstellungen für die zugeordnete SharePoint-Website wie folgt übereinstimmen:

|Bezeichnungseinstellung|Einstellung für die SharePoint-Website|
|:------------|:----------------------|
|**Office 365-Gruppenbesitzer dürfen Personen außerhalb der Organisation zur Gruppe hinzufügen** ausgewählt|**Neue und vorhandene Gäste** (Standard für neue Teams)|
|**Office 365-Gruppenbesitzer dürfen Personen außerhalb der Organisation zur Gruppe hinzufügen** nicht ausgewählt|**Nur Personen in Ihrer Organisation**|

Außerdem wird der standardmäßige Linktyp für die Freigabe aktualisiert, um das Risiko zu verringern, dass Dateien und Ordner versehentlich für ein breiteres Publikum freigegeben werden als beabsichtigt.

So aktualisieren Sie Websiteeinstellungen
1. Öffnen Sie das [SharePoint Admin Center](https://admin.microsoft.com/sharepoint).
2. Klicken Sie unter **Websites** auf **Aktive Websites**.
3. Klicken Sie auf die dem Team zugeordnete Website.
4. Klicken Sie auf der Registerkarte **Richtlinien** unter **Externe Freigabe** auf **Bearbeiten**.
5. Wenn Sie beim Erstellen der Vertraulichkeitsbezeichnung die Gastfreigabe zugelassen haben, stellen Sie sicher, dass **Neue und vorhandene Gäste** ausgewählt ist. Wenn Sie beim Erstellen der Bezeichnung keine Freigabe zugelassen haben, wählen Sie **Nur Personen in Ihrer Organisation** aus.
6. Deaktivieren Sie unter "Standardmäßiger Freigabe-Linktyp" das Kontrollkästchen **Identisch mit der Einstellung auf Organisationsebene**, und wählen Sie **Personen mit vorhandenem Zugriff** aus.
7. Klicken Sie auf **Speichern**.

#### <a name="private-channels"></a>Private Kanäle

Wenn Sie dem Team private Kanäle hinzufügen, erstellt jeder private Kanal eine neue SharePoint-Website mit den Standardeinstellungen für die Freigabe. Diese Websites werden im SharePoint Online Admin Center nicht angezeigt, daher müssen Sie das Cmdlet [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell mit den folgenden Parametern verwenden, um die Gast-Freigabeeinstellungen zu aktualisieren:

- `-SharingCapability Disabled` um die Gastfreigabe zu deaktivieren (standardmäßig aktiviert)
- `-DefaultSharingLinkType Internal` um den standardmäßigen Freigabelink zu *Bestimmte Personen* zu ändern

Wenn Sie nicht beabsichtigen, private Kanäle für Ihr Team zu verwenden, können Sie die Möglichkeit für Teammitglieder deaktivieren, solche Kanäle unter **Mitgliedsberechtigungen** in [Team-Einstellungen](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc) zu erstellen.

### <a name="site-sharing-settings"></a>Freigabeeinstellungen für Websites

Um sicherzustellen, dass die SharePoint-Website nicht mit Personen geteilt wird, die nicht Mitglieder des Teams sind, schränken Sie die Freigabe auf die Besitzer ein. Außerdem beschränken wir das Freigeben von Dateien und Ordnern auf die Teambesitzer. Auf diese Weise wird sichergestellt, dass die Besitzer informiert sind, wenn eine Datei an jemanden außerhalb des Teams freigegeben wird.

So beschränken Sie die Websitefreigabe auf die Besitzer
1. Gehen Sie in Teams zur Registerkarte **Allgemein** des Teams, das Sie aktualisieren möchten.
2. Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.
3. Klicken Sie auf die drei Punkte "(…)" und dann auf **In SharePoint öffnen**.
4. Klicken Sie in der Symbolleiste der zugrunde liegenden SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.
5. Klicken Sie im Bereich "Websiteberechtigungen" unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.
6. Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus, und klicken Sie dann auf **Speichern**.

### <a name="custom-site-permissions"></a>Benutzerdefinierte Website-Berechtigungen

Wenn Sie Personen mit Leseberechtigungen zur Vertraulichkeitsbezeichnung hinzugefügt haben, können Sie diese der SharePoint-Website mit Lesezugriff hinzufügen, damit Sie einfach auf die Dateien zugreifen können.

So fügen Sie Benutzern zur Website hinzu
1. Klicken Sie in der Website auf das Zeichen für die Einstellungen und anschließend auf **Websiteberechtigungen**.
2. Klicken Sie auf **Personen einladen** und klicken Sie dann auf **Nur Website freigeben**.
3. Geben Sie die Namen der Benutzer und Gruppen ein, die Sie einladen möchten.
4. Ändern Sie für jede hinzugefügte Person oder Gruppe deren Berechtigungen von **Bearbeiten** auf **Lesen**.
5. Wählen Sie aus, ob Sie eine E-Mail mit einem Link zur Website senden möchten.
6. Klicken Sie auf **Hinzufügen**.

## <a name="additional-protections"></a>Zusätzliche Schutzfunktionen

Microsoft 365 bietet zusätzliche Methoden zum Schützen Ihrer Inhalte. Prüfen Sie, ob die folgenden Optionen zur Verbesserung der Sicherheit in Ihrer Organisation beitragen würden.

- Lassen Sie Ihre Gastbenutzer den [Nutzungsbedingungen](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use) zustimmen.
- Konfigurieren Sie eine [Richtlinie für Sitzungstimeout](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) für Gastbenutzer.
- Erstellen Sie [Typen vertraulicher Informationen](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) und verwenden Sie [Schutz vor Datenverlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) zum Festlegen von Richtlinien für den Zugriff auf vertrauliche Informationen.
- Verwenden Sie [Azure Active Directory Zugriffsüberprüfungen](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview), um den Zugriff und die Mitgliedschaft des Teams regelmäßig zu überprüfen.

## <a name="drive-user-adoption-for-team-members"></a>Fördern der Benutzerakzeptanz für Teammitglieder

Wenn das Team aktiv ist, ist es an der Zeit, die Benutzerakzeptanz dieses Teams und dessen zusätzlicher Sicherheit für Teammitglieder zu fördern.

## <a name="train-your-users"></a>Schulen Ihrer Benutzer

Mitglieder des Teams können auf das Team und alle zugehörigen Ressourcen zugreifen, b. B. Chats, Besprechungen und andere Apps. Wenn Sie mit Dateien aus dem Abschnitt **Dateien** eines Kanals arbeiten, müssen die Mitglieder des Teams den von ihnen erstellten Dateien eine Vertraulichkeitsbezeichnung zuweisen.

Wird die Bezeichnung auf eine Datei angewendet, ist diese verschlüsselt. Mitglieder des Teams können sie öffnen und in Echtzeit zusammenarbeiten. Wenn die Datei die Website verlässt und an einen böswilligen Benutzer weitergeleitet wird, lässt sich die Datei nur öffnen, und ihr Inhalt kann nur angezeigt werden, wenn die Anmeldeinformationen eines Benutzerkontos angegeben werden, das Mitglied des Teams ist. 

Schulen Sie Ihre Teammitglieder:

- Vermitteln Sie ihnen, wie wichtig es ist, das neue Team für Chats, Besprechungen, Dateien und andere Ressourcen der SharePoint-Website zu nutzen und welche Auswirkungen ein Verlust streng regulierter Daten hat, z. B. rechtliche Konsequenzen, Bußgelder, Ransomware oder Verlust des Wettbewerbsvorteils.
- So greifen Sie auf das Team zu.
- Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.
- Bezeichnen von Dateien mit der richtigen Vertraulichkeitsbezeichnung für das Team.
- Veranschaulichen, wie die Bezeichnung Dateien schützt, auch wenn sie die Website verlassen.

Diese Schulung sollte praktische Übungen umfassen, damit die Teammitglieder diese Funktionen und deren Ergebnisse ausprobieren können.

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a>Durchführen regelmäßiger Verwendungsprüfungen und Behandeln des Feedbacks der Teammitglieder.

In den Wochen nach der Schulung:

- Reagieren Sie umgehend auf Feedback von Teammitgliedern und optimieren Sie die Richtlinien und Konfigurationen.
- Analysieren Sie die Verwendung der Website und vergleichen Sie sie mit den Erwartungen.
- Sicherstellen, dass streng regulierte Dateien korrekt mit der Vertraulichkeitsbezeichnung gekennzeichnet wurden. (Sie können sehen, welchen Dateien eine Bezeichnung zugeordnet ist, indem Sie einen Ordner in SharePoint anzeigen und über die Option **Spalten ein-/ausblenden** > **Spalte hinzufügen** die Spalte **Vertraulichkeit** hinzufügen.

Ihre Benutzer bei Bedarf erneut schulen.

## <a name="see-also"></a>Siehe auch

[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)