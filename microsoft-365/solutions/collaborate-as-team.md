---
title: Zusammenarbeit mit Gästen in einem Team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: Erfahren Sie mehr über die Konfigurationsschritte in Microsoft 365, die notwendig sind, um ein Team für die Zusammenarbeit mit Gästen in Teams bei Aufgaben, Unterhaltungen und Dokumentationen einzurichten.
ms.openlocfilehash: 986f9c1f343c8ccc3d76557291938d170923c89b
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712318"
---
# <a name="collaborate-with-guests-in-a-team"></a>Zusammenarbeit mit Gästen in einem Team

Wenn Sie über Dokumente, Aufgaben und Unterhaltungen hinweg mit Gästen zusammenarbeiten möchten, empfehlen wir Ihnen Microsoft Teams zu verwenden. Teams bietet aale in SharePoint und Office verfügbaren Features für die Zusammenarbeit mit beständigem Chat und einer anpassbaren und erweiterbaren Auswahl an Tools für die Zusammenarbeit in einer vereinheitlichten Benutzererfahrung.

In diesem Artikel werden die einzelnen Konfigurationsschritte von Microsoft 365 behandelt, die erforderlich sind, um ein Team für die Zusammenarbeit mit Gästen einzurichten. Sobald Sie den Gastzugriff konfiguriert haben, können Sie Gäste zu Teams einladen, indem Sie den Schritten in [Gästen in ein Team in Teams einladen](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f) folgen.

## <a name="video-demonstration"></a>Videodemonstration

Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Einstellungen für die Azure Externe Zusammenarbeit

Die Freigabe in Microsoft 365 wird auf der höchsten Ebene von den [Einstellungen für B2B externe Zusammenarbeit in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations) geregelt. Wenn die Gastfreigabe in Azure AD deaktiviert oder eingeschränkt ist, setzt diese Einstellung alle Freigabeeinstellungen, die Sie in Microsoft 365 konfiguriert haben, außer Kraft.

Überprüfen Sie die Einstellungen für B2B externe Zusammenarbeit um sicherzustellen, dass die Freigabe für Gäste nicht blockiert ist.

![Screenshot der Seite mit den Einstellungen für die Azure Active Directory-Organisationsbeziehungen](../media/azure-ad-organizational-relationships-settings.png)

Festlegen der Einstellungen für die Azure Externe Zusammenarbeit

1. Bei Azure Active Directory an [https://aad.portal.azure.com](https://aad.portal.azure.com) anmelden.
2. Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.
3. Klicken Sie auf **Externe Identitäten**.
4. Klicken Sie auf dem Bildschirm **Erste Schritte** im linken Navigationsbereich auf **Einstellungen für die externe Zusammenarbeit**.
5. Stellen Sie sicher, dass sowie **Administratoren und Benutzer mit der Rolle "Einladender" können einladen** als auch **Mitglieder können einladen** beide auf **Ja** festgelegt sind.
6. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

Beachten Sie die Einstellungen im Bereich **Einschränkungen für die Zusammenarbeit**. Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert sind.

Wenn Sie mit Gästen aus mehreren Organisationen arbeiten, könnten Sie möglicherweise Interesse daran haben, ihren Zugriff auf Verzeichnisdaten einzuschränken. Dies wird es ihnen verhindern zu sehen, wer sonst noch Gast im Verzeichnis ist. Wählen Sie dazu unter **Einschränkungen des Gastzugriffs** die Einstellung **Gastbenutzer haben eingeschränkten Zugriff auf Eigenschaften und die Mitgliedschaft bei den Einstellungen der Verzeichnisobjekte** oder **Zugriff der Gastbenutzer ist auf Eigenschaften und die Mitgliedschaft bei ihren eigenen Verzeichnisobjekten eingeschränkt**.

## <a name="teams-guest-access-settings"></a>Gastzugriffseinstellungen für Teams

Teams verfügt über einen ein/aus-Master-Schalter für den Gastzugriff und eine Vielzahl an Einstellungen zur Kontrolle dessen, was Gäste in einem Team machen können und was nicht. Der Master-Schalter, **Gastzugriff in Teams ermöglichen** muss auf **An** gestellt sein, damit Gastzugriff in Teams funktioniert.

Stellen Sie sicher, dass der Gastzugriff in Teams aktiviert ist und nehmen Sie Anpassungen an den Gasteinstellungen je nach Ihren geschäftlichen Anforderungen vor. Bedenken Sie, dass sich diese Einstellungen auf alle Teams auswirken.

![Screenshot der Teams-Umschaltfläche für den Gastzugriff](../media/teams-guest-access-toggle-on.png)

So legen Sie die Gastzugriffseinstellungen für Teams fest

1. Melden Sie sich beim Microsoft 365 Admin Center an auf [https://admin.microsoft.com](https://admin.microsoft.com).
2. Klicken Sie im linken Navigationsbereich auf **Alle anzeigen**.
3. Klicken Sie unter **Admin Centers** auf **Teams**.
4. Erweitern Sie im Teams Admin Center **Organisationsweite Einstellungen** im linken Navigationsbereich und klicken Sie auf **Gastzugriff**.
5. Stellen Sie sicher, dass **Gastzugriff in Teams zulassen** auf **Ein** ist.
6. Nehmen Sie alle gewünschten Änderungen an den zusätzlichen Gasteinstellungen vor, und klicken Sie dann auf **Speichern**.

Sobald Sie den Teams-Gastzugriff aktiviert haben, können Sie den Gastzugriff zu einzelnen Teams und deren zugeordneten SharePoint-Websites optional mithilfe von Vertraulichkeitsbeschriftungen steuern. Weitere Informationen finden Sie unter [Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!NOTE]
> Nachdem die Gasteinstellung für Teams eingeschaltet wurde, kann es bis zu vierundzwanzig Stunden dauern, bis sie aktiv wird.

## <a name="microsoft-365-groups-guest-settings"></a>Gasteinstellungen für Microsoft 365-Gruppen

Teams verwendet Microsoft 365-Gruppen für die Teammitgliedschaft. Die Gasteinstellungen für Microsoft 365-Gruppen müssen aktiviert sein, damit der Gastzugriff in Teams funktionieren kann.

![Screenshot der Gasteinstellungen für Microsoft 365-Gruppen im Microsoft 365 Admin Center](../media/office-365-groups-guest-settings.png)

So legt man Gasteinstellungen für Microsoft 365-Gruppen fest

1. Erweitern Sie **Einstellungen** im linken Navigationsbereich des Microsoft 365 Admin Center.
2. Klicken Sie auf **Organisationseinstellungen**.
3. Klicken Sie in der Liste auf **Microsoft 365-Gruppen**.
4. Stellen Sie sicher, dass die Kontrollkästchen bei den Einstellungen **Gruppenbesitzer Personen außerhalb der Organisation zu Microsoft 365-Gruppen als Gäste hinzufügen lassen** und **Mitgliedern von Gästegruppen Zugriff auf Gruppeninhalte gewährleisten** beide aktiviert sind.
5. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Änderungen speichern**.


## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint-Freigabeeinstellungen auf Organisationsebene

Teams-Inhalte wie Dateien, Ordner und Listen werden alle in SharePoint gespeichert. Damit Gäste in Teams Zugriff auf diese Elemente haben, müssen die SharePoint Freigabeeinstellungen auf Organisationsebene die Freigabe mit Gästen ermöglichen.

Die Einstellungen auf Organisationsebene bestimmen, welche Einstellungen für einzelne Websites zur Verfügung stehen, einschließlich Websites, die zu Teams zugeordnet sind. Websiteeinstellungen können nicht passiver sein als die Einstellungen auf Organisationsebene.

Wenn Sie die Freigabe von Dateien und Ordnern mit nicht authentifizierten Personen erlauben möchten, wählen Sie **Jeder** aus. Wenn Sie sicherstellen möchten, dass sich alle Gäste authentifizieren müssen, wählen Sie **Neue und vorhandene Gäste** aus. Wählen Sie die am wenigsten eingeschränkte Einstellung aus, die von jeder Website in Ihrer Organisation benötigt wird.

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


So legt man SharePoint-Freigabeeinstellungen auf Organisationsebene fest

1. Klicken Sie im Microsoft 365 Admin Center im linken Navigationsbereich unter **Admin Center** auf **SharePoint**.
2. Erweitern Sie im SharePoint Admin Center im linken Navigationsbereich **Richtlinien** und klicken Sie dann auf **Freigabe**.
3. Stellen Sie sicher, dass die Externe Freigabe für SharePoint auf **Jeder** oder **Neue und vorhandene Gäste** eingestellt ist.
4. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.


## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint-Standardlinkeinstellungen auf Organisationsebene

Die Standardeinstellungen für die Datei- und -ordnerverknüpfung bestimmen die Verknüpfungsoption, die Benutzern standardmäßig angezeigt wird, wenn sie eine Datei oder einen Ordner freigeben. Benutzer können, wenn sie so möchten, die Verknüpfungsart vor der Freigabe in eine der anderen Optionen ändern.

Bedenken Sie, dass sich diese Einstellung auf alle Teams und SharePoint-Websites in Ihrer Organisation auswirkt.

Wählen Sie eine der folgenden Verknüpfungsarten, die dann standardmäßig ausgewählt wird, wenn Benutzer Dateien und Ordner freigeben:

- **Jeder mit diesem Link** – Wählen Sie diese Option aus, wenn Sie erwarten, dass Sie viele nicht authentifizierte Freigaben von Dateien und Ordnern durchführen werden. Wenn Sie *Jeder*-Links erlauben wollen, aber zufällige nicht authentifizierte Freigaben befürchten, erwägen Sie eine der anderen Optionen als Standard. Diese Verknüpfungsart ist nur verfügbar, wenn Sie die Freigabe auf **Jeder** aktiviert haben.
- **Nur Personen in Ihrer Organisation** – Wählen Sie diese Option, wenn Sie erwarten, dass die meisten Freigaben von Dateien und Ordnern zwischen Personen innerhalb Ihrer Organisation stattfinden werden.
- **Bestimmte Personen** – erwägen Sie diese Option, wenn Sie erwarten, dass Sie viele Dateien und Ordner an Gäste freigeben werden. Dieser Typ von Link arbeitet mit Gästen und erfordert deren Authentifizierung.
 
![Screenshot der Freigabeeinstellungen auf Organisationsebene für Dateien und Ordner in SharePoint und OneDrive](../media/sharepoint-organization-files-folders-sharing-settings.png)


So legt man SharePoint-Standardlinkeinstellungen auf Organisationsebene fest

1. Navigieren Sie zur Seite „Freigabe“ im SharePoint Admin Center.
2. Wählen Sie unter **Datei- und Ordnerlinks** den Link zur Standardfreigabe, den Sie verwenden möchten.
3. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="create-a-team"></a>Team erstellen

Der nächste Schritt ist das Erstellen des Teams, mit dem Sie vorhaben mit Gästen zusammenzuarbeiten.

So erstellt man eine klassische Teamwebsite
1. Klicken Sie in Microsoft Teams auf der Registerkarte **Teams** auf der linken Seite unten auf **Einem Team beitreten oder ein Team erstellen**.
2. Klicken Sie auf **Team erstellen**.
3. Klicken Sie auf **Neuerstellen eines Teams**.
4. Wählen Sie **Privat** oder **Öffentlich** aus.
5. Geben Sie einen Namen und eine Beschreibung für das Team ein, und klicken Sie dann auf **Erstellen**.
6. Klicken Sie auf **Überspringen**.

Wir werden Benutzer später einladen. Als nächstes ist es wichtig, dass Sie die Freigabeeinstellungen auf Websiteebene für die SharePoint-Website, die dem Team zugeordnet ist, überprüfen.

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint-Freigabeeinstellungen auf Websiteebene

Überprüfen Sie die Freigabeeinstellungen auf Websiteebene, um sicherzustellen, dass sie die Zugriffsart zulassen, die Sie für dieses Team eingestellt haben möchten. Wenn Sie z. B. die Einstellungen auf Organisationsebene auf **Jeder** festlegen, von allen Gästen jedoch wollen, dass sie sich für dieses Team authentifizieren, stellen Sie sicher, dass die Freigabeeinstellungen auf Websiteebene auf **Neue und vorhandene Gäste** festgelegt sind.

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

So legt man Freigabeeinstellungen auf Websiteebene fest
1. Erweitern Sie im SharePoint Admin Center links im Navigationsbereich **Websites** und klicken Sie auf **Aktive Websites**.
2. Wählen Sie die Site des soeben erstellten Teams aus.
3. Klicken Sie ... und wählen Sie **Freigabe** aus.
4. Vergewissern Sie sich, dass die Freigabe auf **Jeder** oder **Neue und vorhandene Gäste** festgelegt ist.
5. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="invite-users"></a>Benutzer einladen

Einstellungen für die Gastfreigabe sind nun konfiguriert, Sie können also mit dem Hinzufügen von internen Benutzern und Gästen zu Ihrem Team anfangen. 

So lädt man interne Benutzer in ein Team ein
1. Klicken Sie im Team auf **Weitere Optionen** (**\*\*\***) und dann auf **Mitglieder hinzufügen**.
2. Geben Sie den Namen der Person ein, die Sie einladen möchten.
3. Klicken Sie auf **Hinzufügen** und dann auf **Schließen**.

Sie kann man Gäste zu einem Team hinzufügen
1. Klicken Sie im Team auf **Weitere Optionen** (**\*\*\***) und dann auf **Mitglieder hinzufügen**.
2. Geben Sie die E-Mail-Adresse des Gasts ein, die Sie einladen möchten.
3. Klicken Sie auf **Bearbeiten von Gastbenutzerinformationen**.
4. Geben Sie den vollständigen Namen des Gasts ein und klicken Sie auf das Häkchen.
5. Klicken Sie auf **Hinzufügen** und dann auf **Schließen**.

## <a name="see-also"></a>Siehe auch

[Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer](best-practices-anonymous-sharing.md)

[Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste](share-limit-accidental-exposure.md)

[Erstellen einer sicheren Gastfreigabeumgebung](create-secure-guest-sharing-environment.md)

[Erstellen eines B2B-Extranets mit verwalteten Gästen](b2b-extranet.md)

[SharePoint- und OneDrive-Integration in Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[Freigabeoptionen werden abgeblendet, wenn von SharePoint oder OneDrive freigegeben wird](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
