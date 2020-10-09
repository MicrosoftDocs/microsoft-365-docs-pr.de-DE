---
title: Konfigurieren von Teams mit grundlegendem Schutz
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Hier erfahren Sie, wie Sie Teams mit grundlegendem Schutz bereitstellen.
ms.openlocfilehash: ac6974b5625a4eff0fcd11a17c4607a7c2caf97f
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398865"
---
# <a name="configure-teams-with-baseline-protection"></a>Konfigurieren von Teams mit grundlegendem Schutz

In diesem Artikel wird erläutert, wie Teams mit eine grundlegenden Schutzebene bereitgestellt werden. Auf dieser Ebene können die Benutzer eine Vielzahl von Optionen für die Zusammenarbeit nutzen und gleichzeitig die Verwaltung von Berechtigungen verbessern sowie grundlegende Schutzmaßnahmen gegen versehentliche Freigabe bieten. Empfohlene Schutzmaßnahmen für diese Stufe umfassen Richtlinien für den Identitäts- und Gerätezugriff sowie Schutz vor Schadsoftware. Darüber hinaus können Sie bei Bedarf bedingte Zugriffsrichtlinien und Datenschutzbestimmungen anwenden.

## <a name="initial-protections"></a>Erste Schutzmaßnahmen

Als Erstes wird empfohlen, grundlegende Identitäts- und Gerätezugriffsrichtlinien zu konfigurieren. Einzelheiten hierzu finden Sie unter [Richtlinienempfehlungen zum Schützen von Teams-Chats, -Gruppen und -Dateien](../security/office-365-security/teams-access-policies.md).

Außerdem empfehlen wir die Aktivierung der grundlegenden erweiterten Bedrohungsschutzfeatures, um die Schadsoftware in Dokumenten, Anlagen und Links zu schützen. Wir empfehlen, jede der Optionen in der folgenden Tabelle zu aktivieren.

|Option|Informationen|
|:------|:-----------|
|Sichere Anlagen in ATP für SPO, OneDrive und Teams|[Office 365 ATP-Feature für sichere Anlagen](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br>[Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)|
|Sichere Dokumente in ATP|[Sichere Dokumente in Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)|
|ATP-Feature für sichere Links für Teams|[Office 365 Sichere Links in Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams)<br>[ATP-sichere Links in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)|

## <a name="teams-guest-sharing"></a>Teams-Gastfreigabe

In jeder der Ebenen haben wir die Möglichkeit, die Freigabe für Personen außerhalb Ihrer Organisation zu gestatten. Bei den vertraulichen und hochsensiblen Kategorien haben wir die Möglichkeit, die Gastfreigabe auf Teamebene durch Verwenden von Vertraulichkeitsbeschriftungen zu deaktivieren. Die Einstellung für die Gastfreigabe auf Organisationsebene muss aktiviert sein, damit die Gastfreigabe überhaupt in Teams funktioniert.

![Screenshot der Teams-Umschaltfläche für den Gastzugriff](../media/teams-guest-access-toggle-on.png)

So legen Sie die Gastzugriffseinstellungen für Teams fest

1. Melden Sie sich beim Microsoft 365 Admin Center an auf [https://admin.microsoft.com](https://admin.microsoft.com).
2. Klicken Sie in der linken Navigationsleiste auf **Alle anzeigen**.
3. Klicken Sie unter **Admin Centers** auf **Teams**.
4. Erweitern Sie im Teams Admin Center **Organisationsweite Einstellungen** in der linken Navigationsleiste und klicken Sie auf **Gastzugriff**.
5. Stellen Sie sicher, dass **Gastzugriff in Teams zulassen** auf **Ein** ist.
6. Nehmen Sie alle gewünschten Änderungen an den zusätzlichen Gasteinstellungen vor, und klicken Sie dann auf **Speichern**.

> [!NOTE]
> Es könnte bis zu vierundzwanzig Stunden dauern, bis die Gasteinstellung für Teams aktiv wird, nachdem sie eingeschaltet wurde.

Die Gastfreigabe ist für Office 365-Gruppen und Microsoft Office SharePoint Online standardmäßig aktiviert. Wenn Sie jedoch zuvor eine der Einstellungen für die Gastfreigabe für Ihre Organisation geändert haben, empfiehlt es sich, [Zusammenarbeit mit Gästen in einem Team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) zu prüfen, um sicherzustellen, dass die Gastfreigabe in Teams zur Verfügung steht.

## <a name="site-and-file-sharing"></a>Website- und Dateifreigabe

Um das Risiko zu verringern, dass Dateien oder Ordner versehentlich für Personen außerhalb Ihrer Organisation freigegeben werden, sollten Sie den standardmäßigen Freigabelink für Microsoft Office SharePoint Online auf *Nur Personen in Ihrer Organisation* setzen. (Wenn Benutzer externe Freigaben vornehmen müssen und die Gastfreigabe aktiviert ist, können Sie den Linktyp beim Freigeben weiterhin ändern.)

So ändern Sie den standardmäßigen Freigabelink
1. Öffnen Sie das [SharePoint Admin Center](https://admin.microsoft.com/sharepoint).
2. Klicken Sie unter **Richtlinien** auf **Freigabe**.
3. Wählen Sie unter **Datei- und Ordnerlinks** die Option **Nur Personen in Ihrer Organisation** aus.
4. Klicken Sie auf **Speichern**.

Für eine optimale Benutzererfahrung empfiehlt es sich außerdem, [SharePoint- und OneDrive-Integration in Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) zu aktivieren.

## <a name="create-a-team"></a>Ein Team erstellen

Eine zusätzliche Konfiguration für die grundlegende Schutzebene erfolgt auf der SharePoint-Website, die einem Team zugeordnet ist. [Erstellen Sie ein öffentliches oder privates Team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b), bevor Sie mit dem nächsten Abschnitt fortfahren.

## <a name="site-sharing-settings"></a>Freigabeeinstellungen für Websites

Standardmäßig können Mitglieder einer SharePoint-Website andere Benutzer zur Website einladen. Wenn eine Website zu einem Team gehört, werden Teammitglieder als Websitemitglieder hinzugefügt. Personen, die direkt zur Website hinzugefügt wurden, haben jedoch keinen Zugriff auf den Rest des Teams. Aus diesem Grund empfiehlt es sich, Berechtigungen ausschließlich über das Team zu verwalten.

Um die Berechtigungsverwaltung zu unterstützen, empfiehlt es sich, die zugeordnete Website so zu konfigurieren, dass sie nur Besitzern das Freigeben der Website selbst gestattet. Auf diese Weise wird die Verwaltung von Berechtigungen vereinfacht und der Zugriff von Personen ohne Wissen des Teambesitzers verhindert. Führen Sie diese Vorgehensweise für jedes Team aus, das einen grundlegenden Schutz erfordert.

So aktualisieren Sie die Freigabeeinstellungen der Website
1. Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.
2. Klicken Sie auf **In SharePoint öffnen**.
3. Klicken Sie in der Symbolleiste der SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.
4. Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.
5. Wählen Sie unter **Freigabeberechtigungen** die Option **Websitebesitzer und -mitglieder sowie Personen mit Bearbeitungsberechtigungen können Dateien und Ordner freigeben, aber nur Websitebesitzer können die Website freigeben**, und klicken Sie dann auf **Speichern**.

## <a name="additional-protections"></a>Zusätzliche Schutzfunktionen

Microsoft 365 bietet zusätzliche Methoden zum Schützen Ihrer Inhalte. Prüfen Sie, ob die folgenden Optionen zur Verbesserung der Sicherheit in Ihrer Organisation beitragen würden.

- Lassen Sie Ihre Gastbenutzer den [Nutzungsbedingungen](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use) zustimmen.
- Konfigurieren Sie eine [Richtlinie für Sitzungstimeout](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) für Gastbenutzer.
- Erstellen Sie [Typen vertraulicher Informationen](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) und verwenden Sie [Schutz vor Datenverlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) zum Festlegen von Richtlinien für den Zugriff auf vertrauliche Informationen.

## <a name="see-also"></a>Siehe auch

[Verwalten von Besprechungsrichtlinien in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)

[Erste Schritte mit dem Insider-Risikomanagement](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure)
