---
title: Zusammenarbeit mit Gästen an einem Dokument
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: Hier erfahren Sie, wie Sie mit Gästen in einem Dokument in SharePoint und OneDrive zusammenarbeiten.
ms.openlocfilehash: 139533b2d7bf65ddd9584007a5ac03800c731d0b
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604785"
---
# <a name="collaborate-with-guests-on-a-document"></a>Zusammenarbeit mit Gästen an einem Dokument

Wenn Sie mit Personen außerhalb Ihrer Organisation in Dokumenten in SharePoint oder OneDrive zusammenarbeiten müssen, können Sie Ihnen einen Freigabe Link an das Dokument senden. In diesem Artikel werden die Microsoft 365-Konfigurationsschritte durchlaufen, die erforderlich sind, um Freigabelinks für SharePoint und OneDrive für die Anforderungen Ihrer Organisation einzurichten.

## <a name="video-demonstration"></a>Videodemonstration

Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Azure Organizational Relationships-Einstellungen

Die Freigabe in Microsoft 365 wird auf der höchsten Ebene durch die Einstellungen für organisatorische Beziehungen in Azure Active Directory gesteuert. Wenn die Gast Freigabe in Azure AD deaktiviert oder eingeschränkt ist, werden alle Freigabeeinstellungen, die Sie in Microsoft 365 konfigurieren, außer Kraft gesetzt.

Überprüfen Sie die Einstellungen für Organisationsbeziehungen, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.

![Screenshot der Seite mit den Einstellungen für die Azure Active Directory-Organisationsbeziehungen](../media/azure-ad-organizational-relationships-settings.png)

So legen Sie Einstellungen für die Organisationsbeziehung fest

1. Melden Sie sich bei Microsoft Azure [https://portal.azure.com](https://portal.azure.com)an an.
2. Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.
3. Klicken Sie im Bereich **Übersicht** auf **Organisationsbeziehungen**.
4. Klicken Sie im Bereich **Organisationsbeziehungen** auf **Einstellungen**.
5. Stellen Sie sicher, dass **Administratoren und Benutzer in der Rolle "Gast einladender" eingeladen** werden und **Mitglieder einladen können** , beide auf " **Ja**" festgelegt sind.
6. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

Beachten Sie die Einstellungen im Abschnitt Einschränkungen für die **Zusammenarbeit** . Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert werden.

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint-Freigabeeinstellungen auf Organisationsebene

Damit Personen außerhalb Ihrer Organisation Zugriff auf ein Dokument in SharePoint oder OneDrive haben, müssen die Freigabeeinstellungen für SharePoint und OneDrive auf Organisationsebene die Freigabe für Personen außerhalb Ihrer Organisation zulassen.

Die Einstellungen auf Organisationsebene für SharePoint bestimmen, welche Einstellungen für einzelne SharePoint-Websites verfügbar sind. Websiteeinstellungen dürfen nicht so restriktiv wie die Einstellungen auf Organisationsebene sein. Die Einstellung auf Organisationsebene für OneDrive legt fest, welche Freigabeebene in den OneDrive-Bibliotheken der Benutzer verfügbar ist.

Wenn Sie für SharePoint und OneDrive die nicht authentifizierte Datei-und Ordnerfreigabe zulassen möchten, wählen Sie **jeden**aus. Wenn Sie sicherstellen möchten, dass sich Personen außerhalb Ihrer Organisation authentifizieren müssen, wählen Sie **neue und vorhandene Gäste**aus. *Jeder* Link ist die einfachste Möglichkeit zur Freigabe: Personen außerhalb Ihrer Organisation können die Verknüpfung ohne Authentifizierung öffnen und können Sie an andere weitergeben.

Wählen Sie für SharePoint die frei zügigste Einstellung aus, die von einer beliebigen Website in Ihrer Organisation benötigt wird.

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


So legen Sie Freigabeeinstellungen für SharePoint-Organisationsebene fest

1. Klicken Sie im Microsoft 365 Admin Center in der linken Navigationsleiste unter **Admin Centers**auf **SharePoint**.
2. Klicken Sie im SharePoint Admin Center links in der Navigation auf **Freigabe**.
3. Stellen Sie sicher, dass die externe Freigabe für SharePoint oder OneDrive auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist. (Beachten Sie, dass die OneDrive-Einstellung nicht restriktiver als die SharePoint-Einstellung sein kann.)
4. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Standard Link Einstellungen für SharePoint-Organisationsebene

Die Standardeinstellungen für Datei-und Ordnerverknüpfung legen fest, welche Link Option dem Benutzer standardmäßig angezeigt wird, wenn er eine Datei oder einen Ordner freigegeben hat. Benutzer können den Verknüpfungstyp vor der Freigabe bei Bedarf in eine der anderen Optionen ändern.

Beachten Sie, dass sich diese Einstellung auf SharePoint-Websites in Ihrer Organisation sowie auf OneDrive auswirkt.

Wählen Sie den Linktyp aus, der standardmäßig ausgewählt ist, wenn Benutzer Dateien und Ordner freigeben:

- **Jeder, der über den Link verfügt** – wählen Sie diese Option aus, wenn Sie eine Vielzahl von nicht authentifizierten Datei-und Ordner Freigaben erwarten. Wenn Sie *alle* Links zulassen möchten, jedoch über versehentliche nicht authentifizierte Freigaben besorgt sind, sollten Sie eine der anderen Optionen als Standard verwenden. Dieser Linktyp ist nur verfügbar, wenn Sie die Freigabe von **Benutzern** aktiviert haben.
- **Nur Personen in Ihrer Organisation** – wählen Sie diese Option aus, wenn Sie davon ausgehen, dass die meisten Datei-und Ordner Freigaben für Personen in Ihrer Organisation gelten.
- **Bestimmte Personen** – diese Option wird empfohlen, wenn Sie eine Vielzahl von Datei-und Ordner Freigaben für Gäste erwarten. Diese Art von Link funktioniert mit Gästen und erfordert die Authentifizierung.
 
![Screenshot der Freigabeeinstellungen auf Organisationsebene für Dateien und Ordner in SharePoint und OneDrive](../media/sharepoint-organization-files-folders-sharing-settings.png)


So legen Sie die Standard Link Einstellungen für SharePoint und OneDrive auf Organisationsebene fest

1. Navigieren Sie im SharePoint Admin Center zur Seite Freigabe.
2. Wählen Sie unter **Datei-und Ordner Links**den standardmäßigen Freigabe Link aus, den Sie verwenden möchten.
3. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="sharepoint-site-level-sharing-settings"></a>Freigabeeinstellungen für SharePoint-Websiteebene

Wenn Sie Dateien und fodlers in einer SharePoint-Website freigeben, müssen Sie auch die Freigabeeinstellungen auf Websiteebene für diese Website überprüfen.

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

So legen Sie Freigabeeinstellungen auf Websiteebene fest
1. Erweitern Sie im SharePoint Admin Center links in der Navigation **Sites** und klicken Sie auf **Aktive Sites**.
2. Wählen Sie die Website aus, die Sie soeben erstellt haben.
3. Klicken Sie im Menüband auf **Freigabe**. 
4. Stellen Sie sicher, dass die Freigabe auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.
5. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="invite-users"></a>Benutzer einladen

Die Einstellungen für die Gast Freigabe sind jetzt konfiguriert, sodass Benutzer nun Dateien und Ordner für Personen außerhalb Ihrer Organisation freigeben können. Weitere Informationen finden Sie unter [Freigeben von OneDrive-Dateien und-Ordnern](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) und Freigeben von [SharePoint-Dateien oder-Ordnern](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .

## <a name="see-also"></a>Siehe auch

[Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer](best-practices-anonymous-sharing.md)

[Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste](share-limit-accidental-exposure.md)