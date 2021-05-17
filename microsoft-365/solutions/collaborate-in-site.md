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
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Erfahren Sie mehr Microsoft 365 Konfigurationsschritte, die zum Einrichten einer SharePoint für die Zusammenarbeit mit Gästen erforderlich sind.
ms.openlocfilehash: fd3cf55b3d95a5c79b9bd4d7c55855f7d73fc0d2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904648"
---
# <a name="collaborate-with-guests-in-a-site"></a>Zusammenarbeit mit Gästen in einer Website

Wenn Sie mit Gästen in Dokumenten, Daten und Listen zusammenarbeiten müssen, können Sie eine SharePoint verwenden. Moderne SharePoint sind mit Microsoft 365-Gruppen verbunden und können die Websitemitgliedschaft verwalten und zusätzliche Tools für die Zusammenarbeit bereitstellen, z. B. ein freigegebenes Postfach und einen Kalender.

In diesem Artikel werden die erforderlichen Konfigurationsschritte Microsoft 365, um eine SharePoint für die Zusammenarbeit mit Gästen zu erstellen.

## <a name="video-demonstration"></a>Videodemonstration

Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Einstellungen für die externe Zusammenarbeit in Azure

Die Freigabe in Microsoft 365 wird auf der höchsten Ebene von den [Einstellungen für B2B externe Zusammenarbeit in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations) geregelt. Wenn die Gastfreigabe in Azure AD deaktiviert oder eingeschränkt ist, setzt diese Einstellung alle Freigabeeinstellungen, die Sie in Microsoft 365 konfiguriert haben, außer Kraft.

Überprüfen Sie die B2B-Einstellungen für die externe Zusammenarbeit, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.

![Screenshot der Azure Active Directory Seite für Einstellungen Zusammenarbeit](../media/azure-ad-organizational-relationships-settings.png)

Festlegen der Einstellungen für die Azure Externe Zusammenarbeit

1. Bei Azure Active Directory an [https://aad.portal.azure.com](https://aad.portal.azure.com) anmelden.
2. Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.
3. Klicken Sie auf **Externe Identitäten**.
4. Klicken Sie auf dem Bildschirm **Erste Schritte** im linken Navigationsbereich auf **Einstellungen für die externe Zusammenarbeit**.
5. Stellen Sie sicher, dass sowie **Administratoren und Benutzer mit der Rolle "Einladender" können einladen** als auch **Mitglieder können einladen** beide auf **Ja** festgelegt sind.
6. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

Beachten Sie die Einstellungen im Bereich **Einschränkungen für die Zusammenarbeit**. Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert sind.

Wenn Sie mit Gästen aus mehreren Organisationen arbeiten, könnten Sie möglicherweise Interesse daran haben, ihren Zugriff auf Verzeichnisdaten einzuschränken. Dies wird es ihnen verhindern zu sehen, wer sonst noch Gast im Verzeichnis ist. Wählen Sie dazu unter **Einschränkungen des Gastzugriffs** die Einstellung **Gastbenutzer haben eingeschränkten Zugriff auf Eigenschaften und die Mitgliedschaft bei den Einstellungen der Verzeichnisobjekte** oder **Zugriff der Gastbenutzer ist auf Eigenschaften und die Mitgliedschaft bei ihren eigenen Verzeichnisobjekten eingeschränkt**.

## <a name="microsoft-365-groups-guest-settings"></a>Gasteinstellungen für Microsoft 365-Gruppen

Moderne SharePoint verwenden Microsoft 365 Gruppen, um den Websitezugriff zu steuern. Die Microsoft 365 Gruppen-Gasteinstellungen müssen aktiviert sein, damit der Gastzugriff auf den SharePoint funktioniert.

![Screenshot der Gasteinstellungen für Microsoft 365-Gruppen im Microsoft 365 Admin Center](../media/office-365-groups-guest-settings.png)

So legt man Gasteinstellungen für Microsoft 365-Gruppen fest

1. Erweitern Sie **Einstellungen** im linken Navigationsbereich des Microsoft 365 Admin Center.
2. Klicken Sie auf **Organisationseinstellungen**.
3. Klicken Sie in der Liste auf **Microsoft 365-Gruppen**.
4. Stellen Sie sicher, dass die Kontrollkästchen bei den Einstellungen **Gruppenbesitzer Personen außerhalb der Organisation zu Microsoft 365-Gruppen als Gäste hinzufügen lassen** und **Mitgliedern von Gästegruppen Zugriff auf Gruppeninhalte gewährleisten** beide aktiviert sind.
5. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Änderungen speichern**.

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint freigabeeinstellungen auf Organisationsebene

Damit Gäste Zugriff auf SharePoint haben, müssen die SharePoint Freigabeeinstellungen auf Organisationsebene die Freigabe für Gäste zulassen.

Die Einstellungen auf Organisationsebene bestimmen die Einstellungen, die für einzelne Websites verfügbar sein werden. Websiteeinstellungen können nicht passiver sein als die Einstellungen auf Organisationsebene.

Wenn Sie die nicht authentifizierte Datei- und Ordnerfreigabe zulassen möchten, wählen Sie **Jeder aus.** Wenn Sie sicherstellen möchten, dass alle Personen außerhalb Ihrer Organisation authentifiziert werden müssen, wählen Sie **Neu und vorhandene Gäste aus.** Wählen Sie die am wenigsten eingeschränkte Einstellung aus, die von jeder Website in Ihrer Organisation benötigt wird.

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


So legt man SharePoint-Freigabeeinstellungen auf Organisationsebene fest

1. Klicken Sie im Microsoft 365 Admin Center im linken Navigationsbereich unter **Admin Center** auf **SharePoint**.
2. Klicken Sie SharePoint Admin Center im linken Navigationsbereich unter **Richtlinien** auf **Freigeben.**
3. Stellen Sie sicher, dass die Externe Freigabe für SharePoint auf **Jeder** oder **Neue und vorhandene Gäste** eingestellt ist.
4. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="create-a-site"></a>Erstellen einer Website

Im nächsten Schritt erstellen Sie die Website, die Sie für die Zusammenarbeit mit Gästen verwenden möchten.

So erstellen Sie eine Website
1. Klicken Sie im SharePoint Admin Center unter **Websites** auf **Aktive Websites**.
2. Klicken Sie auf **Erstellen**.
3. Klicken Sie **auf Teamwebsite**.
4. Geben Sie einen Websitenamen ein, und geben Sie einen Namen für den Gruppenbesitzer (Websitebesitzer) ein.
5. Wählen **Sie unter** Erweiterte Einstellungen aus, ob diese Website öffentlich oder privat sein soll.
6. Klicken Sie auf **Weiter**.
7. Klicken Sie auf **Fertig stellen**.

Wir werden Benutzer später einladen. Als Nächstes ist es wichtig, die Freigabeeinstellungen auf Websiteebene für diese Website zu überprüfen.

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint-Freigabeeinstellungen auf Websiteebene

Überprüfen Sie die Freigabeeinstellungen auf Websiteebene, um sicherzustellen, dass sie die Art des Zugriffs zulassen, die Sie für diese Website wünschen. Wenn Sie beispielsweise die Einstellungen auf Organisationsebene auf **Jeder** festlegen, aber alle Gäste für diese Website authentifizieren sollen, stellen Sie sicher, dass die Freigabeeinstellungen auf Websiteebene auf Neu und vorhandene Gäste festgelegt **sind.**

Beachten Sie, dass die Website nicht für nicht authentifizierte Personen freigegeben werden kann (**Einstellung** Jeder), aber einzelne Dateien und Ordner können.

Sie können auch [Vertraulichkeitsbezeichnungen verwenden, um einstellungen für die](../compliance/sensitivity-labels-teams-groups-sites.md)externe Freigabe für SharePoint steuern.

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

So legt man Freigabeeinstellungen auf Websiteebene fest
1. Erweitern Sie im SharePoint Admin Center links in der Navigation **Sites** und klicken Sie auf **Aktive Sites**.
2. Wählen Sie die Website aus, die Sie freigeben möchten.
3. Klicken Sie auf ..., und klicken Sie auf **Freigeben.**
4. Vergewissern Sie sich, dass die Freigabe auf **Jeder** oder **Neue und vorhandene Gäste** festgelegt ist.
5. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="invite-users"></a>Benutzer einladen

Die Einstellungen für die Gastfreigabe sind jetzt konfiguriert, sodass Sie mit dem Hinzufügen interner Benutzer und Gäste zu Ihrer Website beginnen können. Der Websitezugriff wird über die zugeordnete Microsoft 365 gesteuert, sodass wir dort Benutzer hinzufügen.

So laden Sie interne Benutzer zu einer Gruppe ein
1. Navigieren Sie zu der Website, auf der Sie Benutzer hinzufügen möchten.
2. Klicken **Sie oben** rechts auf Elemente, der die Mitgliederanzahl an kennzeichnet.
3. Klicken Sie auf **Mitglieder hinzufügen**.
4. Geben Sie die Namen oder E-Mail-Adressen der Benutzer ein, die Sie zur Website einladen möchten, und klicken Sie dann auf **Speichern**.

Gäste können nicht von der Website hinzugefügt werden. Sie müssen sie mithilfe von Outlook im Web hinzufügen. Klicken Sie daher als Voraussetzung für das Hinzufügen und Einladen von Gästen zu einer Gruppe auf die URL der Website in der **SPALTE URL,**  um zur websitespezifischen Seite zu navigieren. Klicken Sie auf dieser Seite auf das Symbol für das **Startfeld** der App, und wählen **Sie Outlook**. Dies ist der Bildschirm, von dem aus Sie Gäste in eine Gruppe einladen können, für die das verfahren unten beschrieben wird.

So laden Sie Gäste zu einer Gruppe ein
1. Klicken **Sie unter Gruppen** auf die Gruppe, zu der Sie Gäste einladen möchten.
2. Öffnen Sie die Visitenkarte der Gruppe, **klicken** Sie oben rechts auf Den Link Mitglieder (der Link, der die Mitgliederanzahl kennzeichnet).
3. Klicken **Sie auf Mitglieder hinzufügen**.
4. Geben Sie die E-Mail-Adressen der Gäste ein, die Sie einladen möchten, und klicken Sie dann auf **Hinzufügen.**
5. Klicken Sie auf **Schließen**.
Beachten Sie, dass  Sie nur dann auf Schließen klicken müssen, wenn Sie nicht der Besitzer der Gruppe sind und Sie daher den Gast nicht zur Gruppe hinzufügen dürfen. In solchen Fällen wird die Anforderung, den Gast zur Gruppe hinzuzufügen, zur Genehmigung an den Gruppenbesitzer übertragen.

## <a name="see-also"></a>Siehe auch

[Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer](best-practices-anonymous-sharing.md)

[Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste](share-limit-accidental-exposure.md)

[Erstellen einer sicheren Gastfreigabeumgebung](create-secure-guest-sharing-environment.md)

[Erstellen eines B2B-Extranets mit verwalteten Gästen](b2b-extranet.md)

[SharePoint- und OneDrive-Integration in Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview)