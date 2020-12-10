---
title: Zusammenarbeit mit Gästen an einem Dokument
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
localization_priority: Normal
f1.keywords: NOCSH
description: In diesem Artikel erfahren Sie, wie Sie mit Gästen in einem Dokument in SharePoint und OneDrive zusammenarbeiten.
ms.openlocfilehash: bb97beaacf6a433e4fc5c38a897327d1e359ffb1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613514"
---
# <a name="collaborate-with-guests-on-a-document"></a>Zusammenarbeit mit Gästen an einem Dokument

Wenn Sie mit Personen außerhalb Ihrer Organisation in Dokumenten in SharePoint oder OneDrive zusammenarbeiten müssen, können Sie Ihnen einen Freigabe Link an das Dokument senden. In diesem Artikel werden die Microsoft 365-Konfigurationsschritte durchlaufen, die erforderlich sind, um Freigabe-Links für SharePoint und OneDrive für die Anforderungen Ihrer Organisation einzurichten.

## <a name="video-demonstration"></a>Videodemonstration

Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Azure Organizational Relationships-Einstellungen

Die Freigabe in Microsoft 365 wird auf der höchsten Ebene durch die [Einstellungen für organisatorische Beziehungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)gesteuert. Wenn die Gast Freigabe in Azure AD deaktiviert oder eingeschränkt ist, überschreibt diese Einstellung alle Freigabeeinstellungen, die Sie in Microsoft 365 konfigurieren.

Überprüfen Sie die Einstellungen für Organisationsbeziehungen, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.

![Screenshot der Seite mit den Einstellungen für die Azure Active Directory-Organisationsbeziehungen](../media/azure-ad-organizational-relationships-settings.png)

So legen Sie Einstellungen für die Organisationsbeziehung fest

So legen Sie Einstellungen für die externe Zusammenarbeit fest

1. Melden Sie sich bei Azure Active Directory unter an [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.
3. Klicken Sie auf **externe Identitäten**.
4. Klicken Sie auf dem Bildschirm **Erste Schritte** im linken Navigationsbereich auf **Einstellungen für externe Zusammenarbeit**.
5. Stellen Sie sicher, dass **Administratoren und Benutzer in der Rolle "Gast einladender" eingeladen** werden und **Mitglieder einladen können** , beide auf " **Ja**" festgelegt sind.
6. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

Beachten Sie die Einstellungen im Abschnitt Einschränkungen für die **Zusammenarbeit** . Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert werden.

Wenn Sie mit Gästen aus mehreren Organisationen zusammenarbeiten, möchten Sie möglicherweise die Möglichkeit zum Zugriff auf Verzeichnisdaten einschränken. Dadurch wird verhindert, dass Sie sehen, wer sonst ein Gast im Verzeichnis ist. Wählen Sie dazu unter **Benutzerzugriffs Einschränkungen** für Gast die Option **Gastbenutzer haben begrenzten Zugriff auf Eigenschaften und Mitgliedschaft in Verzeichnisobjekt Einstellungen** oder **Gastbenutzer Zugriff ist auf Eigenschaften und Mitgliedschaften ihrer eigenen Verzeichnisobjekte beschränkt**.

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint-Freigabeeinstellungen auf Organisationsebene

Damit Personen außerhalb Ihrer Organisation Zugriff auf ein Dokument in SharePoint oder OneDrive haben, müssen die Freigabeeinstellungen für SharePoint und OneDrive auf Organisationsebene die Freigabe für Personen außerhalb Ihrer Organisation zulassen.

Die Einstellungen auf Organisationsebene für SharePoint bestimmen die Einstellungen, die für einzelne SharePoint-Websites verfügbar sind. Websiteeinstellungen dürfen nicht so restriktiv wie die Einstellungen auf Organisationsebene sein. Die Einstellung auf Organisationsebene für OneDrive bestimmt die Freigabeebene, die in den OneDrive-Bibliotheken der Benutzer verfügbar sein wird.

Wenn Sie für SharePoint und OneDrive die nicht authentifizierte Datei-und Ordnerfreigabe zulassen möchten, wählen Sie **jeden** aus. Wenn Sie sicherstellen möchten, dass sich Personen außerhalb Ihrer Organisation authentifizieren müssen, wählen Sie **neue und vorhandene Gäste** aus. *Jeder* Links ist die einfachste Möglichkeit zur Freigabe: Personen außerhalb Ihrer Organisation können die Verknüpfung ohne Authentifizierung öffnen und können Sie an andere weitergeben.

Wählen Sie für SharePoint die frei zügigste Einstellung aus, die von einer beliebigen Website in Ihrer Organisation benötigt wird.

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


So legen Sie Freigabeeinstellungen für SharePoint auf Organisationsebene fest

1. Klicken Sie im Microsoft 365 Admin Center im linken Navigationsbereich unter **Admin Centers** auf **SharePoint**.
2. Klicken Sie im SharePoint Admin Center im linken Navigationsbereich unter **Richtlinien** auf **Freigabe**.
3. Stellen Sie sicher, dass die externe Freigabe für SharePoint oder OneDrive auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist. (Beachten Sie, dass die OneDrive-Einstellung nicht restriktiver als die SharePoint-Einstellung sein kann.)
4. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Standard Link Einstellungen für SharePoint auf Organisationsebene

Die Standardeinstellungen für Datei-und Ordnerverknüpfung bestimmen die Verknüpfungsoption, die Benutzern standardmäßig angezeigt wird, wenn Sie eine Datei oder einen Ordner freigeben. Benutzer können den Verknüpfungstyp in eine der anderen Optionen vor der Freigabe ändern, falls gewünscht.

Beachten Sie, dass sich diese Einstellung auf SharePoint-Websites in Ihrer Organisation sowie auf OneDrive auswirkt.

Wählen Sie einen Link von einem der folgenden Typen aus, der dann standardmäßig ausgewählt wird, wenn Benutzer Dateien und Ordner freigeben:

- **Jeder, der über den Link verfügt** – wählen Sie diese Option aus, wenn Sie eine Vielzahl von nicht authentifizierten Datei-und Ordner Freigaben erwarten. Wenn Sie *alle* Links zulassen möchten, jedoch über versehentliche nicht authentifizierte Freigaben besorgt sind, sollten Sie eine der anderen Optionen als Standard verwenden. Dieser Linktyp ist nur verfügbar, wenn Sie die Freigabe von **Benutzern** aktiviert haben.
- **Nur Personen in Ihrer Organisation** – wählen Sie diese Option aus, wenn Sie davon ausgehen, dass die meisten Datei-und Ordner Freigaben für Personen in Ihrer Organisation gelten.
- **Bestimmte Personen** – diese Option wird empfohlen, wenn Sie eine Vielzahl von Datei-und Ordner Freigaben für Gäste erwarten. Diese Art von Link funktioniert mit Gästen und erfordert die Authentifizierung.
 
![Screenshot der Freigabeeinstellungen auf Organisationsebene für Dateien und Ordner in SharePoint und OneDrive](../media/sharepoint-organization-files-folders-sharing-settings.png)


So legen Sie die Standard Link Einstellungen für SharePoint und OneDrive auf Organisationsebene fest

1. Navigieren Sie im SharePoint Admin Center zur Seite Freigabe.
2. Wählen Sie unter **Datei-und Ordner Links** den standardmäßigen Freigabe Link aus, den Sie verwenden möchten.
3. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

Klicken Sie zum Festlegen der Berechtigung für den Freigabe Link unter **Wählen Sie die Berechtigung aus, die standardmäßig für Freigabelinks ausgewählt ist.**

1. Wählen Sie **Ansicht** aus, wenn Sie nicht möchten, dass nicht authentifizierte Benutzer Änderungen an den Dateien und Ordnern vornehmen.
2. Wählen Sie **Bearbeiten** aus, wenn Sie zulassen möchten, dass nicht authentifizierte Benutzer Änderungen an den Dateien und Ordnern vornehmen.

Beachten Sie, dass die beiden obigen premission-Optionen nicht nur für Gäste/externe Benutzer, sondern auch für interne Benutzer angewendet werden können. Die von Ihnen gewählte Berechtigungsoption wird durch selbst Diskretion bestimmt.

So legen Sie Berechtigungen für Links fest, die die Freigabe für beliebige Personen zulassen

1. Unter den **folgenden Links können diese Berechtigungen erteilt werden:** Unterbereich, 
    1. In der Dropdownliste **Dateien** 
        1. Wählen Sie **anzeigen und bearbeiten** aus, wenn Sie zulassen möchten, dass nicht authentifizierte Benutzer Änderungen an den Dateien vornehmen können.
        2. Wählen Sie **Ansicht** aus, wenn Sie nicht möchten, dass nicht authentifizierte Benutzer Änderungen an den Dateien vornehmen.
    2. In der Dropdownliste **Ordner**
        1. Wählen Sie **anzeigen, bearbeiten und hochladen** aus, wenn Sie zulassen möchten, dass nicht authentifizierte Benutzer Änderungen an den Ordnern vornehmen können.
        2. Wählen Sie **Ansicht** aus, wenn Sie nicht möchten, dass nicht authentifizierte Benutzer Änderungen an den Ordnern vornehmen.

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint-Freigabeeinstellungen auf Websiteebene

Wenn Sie Dateien und Ordner in einer SharePoint-Website freigeben, müssen Sie auch die Freigabeeinstellungen auf Websiteebene für diese Website überprüfen.

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

So legen Sie Freigabeeinstellungen auf Websiteebene fest

1. Erweitern Sie im SharePoint Admin Center im linken Navigationsbereich den Knoten **Websites** , und klicken Sie dann auf **aktive Standorte**.
2. Wählen Sie die Website aus, für die Sie Dateien und Ordner für Gäste freigeben möchten.
3. Scrollen Sie nach rechts in der Zeile (in der die ausgewählte Website vorhanden ist), und klicken Sie auf eine beliebige Stelle in der Spalte **externe Freigabe** .
4. Klicken Sie auf der Seite, die sich öffnet, auf Registerkarte **Richtlinien** .
5. Klicken Sie im Bereich **externe Freigabe** auf **Bearbeiten**.
6. Stellen Sie sicher, dass die Freigabe auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.
7. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="invite-users"></a>Benutzer einladen

Einstellungen für die Gast Freigabe sind jetzt konfiguriert; Damit können Benutzer nun Dateien und Ordner für Personen außerhalb Ihrer Organisation freigeben. Weitere Informationen finden Sie unter [Freigeben von OneDrive-Dateien und-Ordnern](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) und Freigeben von [SharePoint-Dateien oder-Ordnern](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .

## <a name="see-also"></a>Siehe auch

[Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer](best-practices-anonymous-sharing.md)

[Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste](share-limit-accidental-exposure.md)

[SharePoint-und OneDrive-Integration mit Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
