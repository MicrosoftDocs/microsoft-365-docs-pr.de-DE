---
title: Zusammenarbeit mit Gästen in einer Website
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- M365solutions
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Hier finden Sie Informationen zu den Microsoft 365-Konfigurationsschritten, die zum Einrichten einer SharePoint-Website für die Zusammenarbeit mit Gästen erforderlich sind.
ms.openlocfilehash: 1f53fa43b6abdfaf21d938bc69db384d173d660e
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160003"
---
# <a name="collaborate-with-guests-in-a-site"></a>Zusammenarbeit mit Gästen in einer Website

Wenn Sie mit Gästen in Dokumenten, Daten und Listen zusammenarbeiten müssen, können Sie eine SharePoint-Website verwenden. Moderne SharePoint-Websites sind mit Microsoft 365-Gruppen verbunden und können die Website Mitgliedschaft verwalten und zusätzliche Tools für die Zusammenarbeit bereitstellen, beispielsweise ein freigegebenes Postfach und einen Kalender.

In diesem Artikel werden die Microsoft 365-Konfigurationsschritte durchlaufen, die erforderlich sind, um eine SharePoint-Website für die Zusammenarbeit mit Gästen einzurichten.

## <a name="video-demonstration"></a>Videodemonstration

Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

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

## <a name="microsoft-365-groups-guest-settings"></a>Microsoft 365 Gruppen-Gast Einstellungen

Moderne SharePoint-Websites verwenden Microsoft 365-Gruppen, um den Website Zugriff zu steuern. Die Gast Einstellungen für Microsoft 365-Gruppen müssen aktiviert sein, damit der Gastzugriff auf SharePoint-Websites funktioniert.

![Screenshot der Gasteinstellungen für Microsoft 365-Gruppen im Microsoft 365 Admin Center](../media/office-365-groups-guest-settings.png)

So legen Sie die Gast Einstellungen für Microsoft 365-Gruppen fest

1. Erweitern Sie im Microsoft 365 Admin Center in der linken Navigationsleiste **Einstellungen**.
2. Klicken Sie auf **Dienste &-Add-ins**.
3. Klicken Sie in der Liste auf **Microsoft 365-Gruppen**.
4. Stellen Sie sicher, dass die Gruppen **Mitglieder außerhalb Ihrer Organisation Zugriff auf Gruppeninhalte** haben und Gruppen **Besitzer Personen außerhalb Ihrer Organisation hinzufügen zulassen** Kontrollkästchen aktiviert sind.
5. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Änderungen speichern**.


## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint-Freigabeeinstellungen auf Organisationsebene

Damit Gästezugriff auf SharePoint-Websites haben, müssen die SharePoint-Freigabeeinstellungen auf Organisationsebene für die Freigabe für Gäste zulässig sein.

Die Einstellungen auf Organisationsebene bestimmen, welche Einstellungen für einzelne Websites verfügbar sind. Websiteeinstellungen dürfen nicht so restriktiv wie die Einstellungen auf Organisationsebene sein.

Wenn Sie die Freigabe nicht authentifizierter Dateien und Ordner zulassen möchten, wählen Sie **jeden**aus. Wenn Sie sicherstellen möchten, dass sich alle Personen außerhalb Ihrer Organisation authentifizieren müssen, wählen Sie **neue und vorhandene Gäste**aus. Wählen Sie die frei zügigste Einstellung aus, die von einer beliebigen Website in Ihrer Organisation benötigt wird.

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


So legen Sie Freigabeeinstellungen für SharePoint-Organisationsebene fest

1. Klicken Sie im Microsoft 365 Admin Center in der linken Navigationsleiste unter **Admin Centers**auf **SharePoint**.
2. Klicken Sie im SharePoint Admin Center links in der Navigation auf **Freigabe**.
3. Stellen Sie sicher, dass die externe Freigabe für SharePoint auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.
4. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="create-a-site"></a>Erstellen einer Website

Im nächsten Schritt erstellen Sie die Website, die Sie für die Zusammenarbeit mit Gästen verwenden möchten.

So erstellen Sie eine Website
1. Klicken Sie im SharePoint Admin Center unter **Websites** auf **Aktive Websites**.
2. Klicken Sie auf **Erstellen**.
3. Klicken Sie auf **Team Website**.
4. Geben Sie einen Websitenamen ein, und geben Sie einen Namen für den Gruppenbesitzer (Websitebesitzer) ein.
5. Wählen Sie unter **Erweiterte Einstellungen**aus, ob es sich um eine öffentliche oder private Website handeln soll.
6. Klicken Sie auf **Weiter**.
7. Klicken Sie auf **Fertig stellen**.

Wir laden Benutzer später ein. Als nächstes ist es wichtig, die Freigabeeinstellungen auf Standortebene für diese Website zu überprüfen.

## <a name="sharepoint-site-level-sharing-settings"></a>Freigabeeinstellungen für SharePoint-Websiteebene

Überprüfen Sie die Freigabeeinstellungen auf Standortebene, um sicherzustellen, dass die gewünschten Zugriffstypen für diese Website zulässig sind. Wenn Sie beispielsweise die Einstellungen auf Organisationsebene auf " **jeder**" festlegen, aber alle Gäste für diese Website authentifizieren möchten, stellen Sie sicher, dass die Freigabeeinstellungen auf Standortebene auf " **neu" und "vorhandene Gäste**" festgelegt sind.

Beachten Sie, dass die Website nicht für nicht authentifizierte Personen freigegeben werden kann (**jede** Einstellung), sondern einzelne Dateien und Ordner können.

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

So legen Sie Freigabeeinstellungen auf Websiteebene fest
1. Erweitern Sie im SharePoint Admin Center links in der Navigation **Sites** und klicken Sie auf **Aktive Sites**.
2. Wählen Sie die Website aus, die Sie soeben erstellt haben.
3. Klicken Sie im Menüband auf **Freigabe**. 
4. Stellen Sie sicher, dass die Freigabe auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.
5. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="invite-users"></a>Benutzer einladen

Die Einstellungen für die Gast Freigabe sind nun konfiguriert, sodass Sie mit dem Hinzufügen interner Benutzer und Gäste zu Ihrer Website beginnen können. Der Website Zugriff wird über die zugehörige Microsoft 365-Gruppe gesteuert, sodass Benutzer dort hinzugefügt werden.

So laden Sie interne Benutzer zu einer Gruppe ein
1. Navigieren Sie zu der Website, auf der Sie Benutzer hinzufügen möchten.
2. Klicken Sie oben rechts auf **Mitglieder** .
3. Klicken Sie auf **Mitglieder hinzufügen**.
4. Geben Sie die Namen oder e-Mail-Adressen der Benutzer ein, die Sie zur Website einladen möchten, und klicken Sie dann auf **Speichern**.

Gastbenutzer können nicht von der Website hinzugefügt werden. Sie müssen Sie mit Outlook im Internet hinzufügen.

So laden Sie Gäste zu einer Gruppe ein
1. Klicken Sie in Outlook im Internet unter **Gruppen**auf die Gruppe, der Sie Mitglieder hinzufügen möchten.
2. Öffnen Sie die Gruppen Visitenkarte, und klicken Sie dann unter **Weitere Optionen** (...) auf **Mitglieder hinzufügen**.
3. Geben Sie die e-Mail-Adressen der Gäste ein, die Sie einladen möchten, und klicken Sie dann auf **Hinzufügen**.
4. Klicken Sie auf **Schließen**.

## <a name="see-also"></a>Siehe auch

[Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer](best-practices-anonymous-sharing.md)

[Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste](share-limit-accidental-exposure.md)

[Erstellen einer sicheren Gastfreigabeumgebung](create-secure-guest-sharing-environment.md)

[Erstellen eines B2B-Extranets mit verwalteten Gästen](b2b-extranet.md)

