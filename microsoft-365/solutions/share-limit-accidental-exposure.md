---
title: Begrenzen der versehentlichen Exposition
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
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: Erfahren Sie, wie Sie die versehentliche Exposition von Informationen bei der Freigabe von Dateien für Personen außerhalb der Organisation begrenzen.
ms.openlocfilehash: 1dffa40a0c21f5f611492d5a098a98f8aaa726a5
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326987"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a>Begrenzen der versehentlichen Exposition von Dateien bei deren Freigabe für Personen außerhalb der Organisation

Wenn Sie Dateien und Ordner für Personen außerhalb Ihrer Organisation freigeben, gibt es verschiedene Optionen, um die Wahrscheinlichkeit zu verringern, dass vertrauliche Informationen versehentlich freigegeben werden. Sie können aus den Optionen in diesem Artikel wählen, um die Anforderungen Ihrer Organisation optimal zu erfüllen.

## <a name="use-best-practices-for-anyone-links"></a>Bewährte Methoden für „Jeder“-Links verwenden

Wenn Personen in Ihrer Organisation eine Freigabe ohne Authentifizierung vornehmen müssen, Sie jedoch befürchten, dass nicht authentifizierte Personen Inhalte ändern, lesen Sie [Bewährte Methoden für die Freigabe ohne Authentifizierung](best-practices-anonymous-sharing.md), um Anleitungen zum Arbeiten mit der Freigabe ohne Authentifizierung in Ihrer Organisation zu erhalten.

## <a name="turn-off-anyone-links"></a>Deaktivieren von "Jeder"-Links

Wir empfehlen, die *Jeder*-Links für den entsprechenden Inhalt aktiviert zu lassen, da dies die einfachste Freigabemöglichkeit ist und das Risiko reduziert, dass Benutzer andere Lösungen außerhalb der Kontrolle Ihrer IT-Abteilung suchen. *Jeder*-Links können an andere weitergeleitet werden, aber Dateizugriff ist nur für diejenigen möglich, die den Link haben.

Wenn Personen von außerhalb der Organisation sich beim Zugreifen auf Inhalte in SharePoint, Gruppen oder Teams authentifizieren sollen, können Sie die *Jeder*-Freigabe deaktivieren. Das verhindert, dass Benutzer Inhalte ohne Authentifizierung freigeben.

Wenn Sie die *Jeder*-Links deaktivieren, können Benutzer Elemente weiterhin mit *Bestimmte Personen*-Links für Gäste freigeben. In diesem Fall müssen sich alle Personen außerhalb der Organisation authentifizieren, bevor sie auf die freigegebenen Inhalte zugreifen können.

Je nach Ihren Anforderungen können Sie *Jeder*-Links für bestimmte Sites oder für Ihre gesamte Organisation deaktivieren.

So deaktivieren Sie *Jeder*-Links für Ihre Organisation
1. Klicken Sie im SharePoint Admin Center links in der Navigation auf **Freigabe**.
2. Legen Sie für die SharePoint-Einstellungen für die externe Freigabe **Neue und vorhandene Gäste** fest.

   ![Screenshot der externen SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. Klicken Sie auf **Speichern**.

So deaktivieren Sie *Jeder*-Links für eine Site
1. Erweitern Sie im SharePoint Admin Center links in der Navigation **Sites** und klicken Sie auf **Aktive Sites**.
2. Wählen Sie die Website aus, die Sie konfigurieren möchten.
3. Klicken Sie im Menüband auf **Freigabe**. 
4. Vergewissern Sie sich, dass die Freigabe auf **Neue und vorhandene Gäste** festgelegt ist.

   ![Screenshot der externen SharePoint-Freigabeeinstellungen auf Websiteebene](../media/sharepoint-site-external-sharing-settings.png)

5. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="domain-filtering"></a>Domänenfilter

Sie können Zulassungs- oder Verweigerungsliste für Domänen verwenden, um festzulegen, welche Domänen Ihre Benutzer bei der Freigabe für Personen außerhalb der Organisation verwenden können.

Mit einer Zulassungsliste können Sie eine Liste der Domänen festlegen, aus denen Benutzer in Ihrer Organisation Inhalte für Personen außerhalb der Organisation freigeben können. Die Freigabe für andere Domänen ist blockiert. Wenn Ihre Organisation nur mit Personen aus einer Liste bestimmter Domänen zusammenarbeitet, können Sie diese Funktion verwenden, um die Freigabe für andere Domänen zu verhindern.

Mit einer Verweigerungsliste können Sie eine Liste der Domänen festlegen, aus denen Benutzer in Ihrer Organisation keine Inhalte für Personen außerhalb der Organisation freigeben können. Die Freigabe der aufgeführten Domänen wird blockiert. Dies kann hilfreich sein, wenn Sie beispielsweise Konkurrenten haben, die Sie daran hindern möchten, auf Inhalte in Ihrer Organisation zuzugreifen.

Die Zulassungs- und Verweigerungslisten wirken sich nur auf die Freigabe für Gäste aus. Benutzer können weiterhin für Personen aus verbotenen Domänen freigeben, indem sie *Jeder*-Links verwenden, wenn Sie diese nicht deaktiviert haben. Für optimale Ergebnisse in Bezug auf die Zulassungs- und Ablehnungslisten für Domänen, ziehen Sie die Deaktivierung von *Jeder*-Links wie oben beschrieben in Betracht.

So richten Sie eine Zulassungs- oder Ablehnungsliste ein
1. Klicken Sie im SharePoint Admin Center links in der Navigation auf **Freigabe**.
2. Aktivieren Sie unter **Erweiterte Einstellungen für externe Freigabe** das Kontrollkästchen **Externe Freigabe nach Domäne einschränken**.
3. Klicken Sie auf **Domänen hinzufügen**.
4. Wählen Sie aus, ob Domänen blockiert werden sollen, geben Sie die Domänen ein, und klicken Sie auf **OK**.

   ![Screenshot der SharePoint-Einstellung "Einschränken der externen Freigabe mithilfe von Domänen"](../media/sharepoint-sharing-block-domain.png)

5. Klicken Sie auf **Speichern**.

Wenn Sie die Freigabe mithilfe von Domänen auf einer höheren Ebene als SharePoint und OneDrive einschränken möchten, [lassen Sie Einladungen in Azure Active Directory für B2B-Benutzer aus bestimmten Organisationen zu oder blockieren Sie sie](/azure/active-directory/b2b/allow-deny-list). (Sie müssen die [SharePoint- und OneDrive-Integration mit Azure AD B2B Preview](/sharepoint/sharepoint-azureb2b-integration-preview) konfigurieren, damit diese Einstellungen für SharePoint und OneDrive wirksam sind.)

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a>Einschränken der Freigabe von Dateien, Ordnern und Websites für Personen außerhalb Ihrer Organisation auf bestimmte Sicherheitsgruppen

Sie können die Freigabe von Dateien, Ordnern und Websites für Personen außerhalb Ihrer Organisation auf Mitglieder einer bestimmten Sicherheitsgruppe einschränken. Dies ist nützlich, wenn Sie die externe Freigabe aktivieren, dafür aber einen Genehmigungsworkflow oder einem Anforderungsprozess festlegen möchten. Alternativ dazu können Sie von Ihren Benutzern verlangen, dass sie einen Schulungskurs absolvieren, bevor sie der Sicherheitsgruppe hinzugefügt werden und ihnen die externe Freigage erlaubt wird.

So schränken Sie die externe Freigabe auf Mitglieder einer Sicherheitsgruppe ein
1. Klicken Sie im [SharePoint Admin Center](https://admin.microsoft.com/sharepoint) links in der Navigation unter **Richtlinien** auf **Freigabe**.
2. Erweitern Sie **Weitere Einstellungen für die externe Freigabe** unter **Externe Freigabe**.

3. Wählen Sie **Ausschließlich Benutzern in bestimmten Sicherheitsgruppen die externe Freigabe erlauben** und dann **Sicherheitsgruppen verwalten** aus.

    ![Screenshot des Bereichs "Sicherheitsgruppen verwalten"](/sharepoint/sharepointonline/media/manage-security-groups.png)

4. Geben Sie im Feld **Sicherheitsgruppe hinzufügen** einen Namen für eine Sicherheitsgruppe ein. Das Feld "Sicherheitsgruppe" wird angezeigt.

5. Wählen Sie neben dem Namen der Sicherheitsgruppe aus der Dropdownliste **kann freigeben für** eine der folgenden Optionen aus:

    - **Nur authentifizierte Gäste** (Standard)
    - **Jeder**

6. Klicken Sie auf **Speichern**.

Dies wirkt sich auf Dateien, Ordner und Sites, aber nicht auf Microsoft 365-Gruppen oder -Teams aus. Wenn Mitglieder Gäste zu einer privaten Microsoft 365-Gruppe oder einem privaten Team in Microsoft Teams einladen, wird die Einladung zur Genehmigung an den Gruppen- oder Teambesitzer gesendet.

## <a name="see-also"></a>Siehe auch

[Erstellen einer sicheren Umgebung für die Gastfreigabe](create-secure-guest-sharing-environment.md)

[Bewährte Methoden zum Freigeben von Dateien und Ordnern für anonyme Benutzer](best-practices-anonymous-sharing.md)
