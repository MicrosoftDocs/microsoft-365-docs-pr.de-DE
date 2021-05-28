---
title: Einrichten von SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Einrichten des Inhaltsverständnisses in Projekt Cortex
ms.openlocfilehash: 7589003505aafb480872b14a09c383cfbe0dff40
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683549"
---
# <a name="set-up-sharepoint-syntex"></a>Einrichten von SharePoint Syntex

Administratoren können das Microsoft 365 Admin Center verwenden, um [Microsoft SharePoint Syntex](index.md) einzurichten. 

Denken Sie vor dem Beginn über Folgendes nach:

- Auf welchen SharePoint-Websites wird die Formularverarbeitung aktiviert? Auf allen, auf einigen oder auf ausgewählten Websites?
- Wie werden Sie Ihr Standard-Inhaltscenter nennen?

Sie können Ihre Einstellungen nach der erstmaligen Einrichtung im Microsoft 365 Admin Center ändern.

Vergewissern Sie sich vor dem Einrichten, dass Sie die beste Möglichkeit zum Einrichten und Konfigurieren des Inhaltsverständnisses in Ihrer Umgebung planen. Sie müssen beispielsweise folgende Entscheidungen treffen:

- Die SharePoint-Websites, auf denen Sie die Verarbeitung von Formularen aktivieren möchten – alle, einige oder ausgewählte Websites.
- Name und Administratoren für Ihr Inhaltscenter

## <a name="requirements"></a>Anforderungen 

> [!NOTE]
> Sie müssen über globale Administrator- oder SharePoint-Administratorberechtigungen verfügen, um auf das Microsoft 365 Admin Center zugreifen und SharePoint Syntex einrichten zu können.

Als Administrator können Sie nach dem Einrichten und in den Verwaltungseinstellungen für das Inhaltsverständnis im Microsoft 365 Admin Center jederzeit Änderungen an den ausgewählten Einstellungen vornehmen.

Wenn Sie beabsichtigen, eine benutzerdefinierte Power Platform-Umgebung zu verwenden, müssen Sie [die App *KI-Generator für Project Cortex* in dieser Umgebung installieren](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) und ihr [KI-Generator-Punkte zuweisen](/power-platform/admin/capacity-add-on), bevor Sie Modelle zur Formularverarbeitung erstellen können.

### <a name="licensing"></a>Lizenzierung

Um SharePoint Syntex verwenden zu können, muss Ihre Organisation ein entsprechendes Abonnement dafür haben, und jedem Benutzer müssen die folgenden Lizenzen zugewiesen sein:

- SharePoint Syntex
- SharePoint Syntex – SPO-Typ
- Gemeinsamer Datendienst für SharePoint Syntex

Wenn Sie Ihr SharePoint Syntex-Abonnement zu einem späteren Zeitpunkt kündigen (oder wenn Ihre Testversion abläuft), können Benutzer kein Dokumentverständnis- oder Formularverarbeitungsmodell mehr erstellen oder ausführen, und die Inhaltscenter-Vorlage ist nicht mehr verfügbar. Zusätzlich werden Terminologiespeicher-Berichte, SKOS-Taxonomie-Importe und Inhaltstyp-Push nicht mehr verfügbar sein. Es werden keine Inhalte gelöscht und die Websiteberechtigungen werden nicht verändert.

### <a name="ai-builder-credits"></a>KI-Generator-Punkte

Wenn Sie 300 oder mehr SharePoint Syntex-Lizenzen für SharePoint Syntex in Ihrer Organisation besitzen, werden Ihnen 1 Million KI-Generator-Punkte zugeteilt. Wenn Sie weniger als 300 Lizenzen besitzen, müssen Sie KI-Generator-Punkte erwerben, um die Formularverarbeitung zu verwenden.

Sie können die für Sie geeignete KI-Generator-Kapazität mit dem [KI-Generator-Rechner](https://powerapps.microsoft.com/ai-builder-calculator) abschätzen.

Wenn Sie planen, eine benutzerdefinierte Power Platform-Umgebung zu verwenden, [weisen Sie dieser Umgebung Guthaben zu](/power-platform/admin/capacity-add-on).

Wechseln Sie zum [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/resources/capacity), um Ihre Punkte und deren Nutzung zu überprüfen.

## <a name="to-set-up-sharepoint-syntex"></a>So richten Sie SharePoint Syntex ein

1. Wählen Sie im Microsoft 365 Admin Center **Setup** aus, und zeigen Sie dann den Abschnitt **Dateien und Inhalte** an.

2. Wählen Sie im Abschnitt **Dateien und Inhalte** > **Inhaltsverständnis automatisieren** aus. Beachten Sie, dass die Verfügbarkeit der Punkte Ihres aktuellen KI-Generators im Bereich **Auf einen Blick** angezeigt wird.<br/>

3. Klicken Sie auf der Seite **Inhaltsverständnis automatisieren** auf **Erste Schritte**, um den Setupvorgang zu durchlaufen. <br/>

    > [!div class="mx-imgBorder"]
    > ![Setup starten](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. Auf der Seite **Formularverarbeitung konfigurieren** können Sie auswählen, ob Sie zulassen möchten, dass Benutzer Formularverarbeitungsmodelle in bestimmten SharePoint-Dokumentbibliotheken erstellen können. Im Menüband "Dokumentbibliothek" wird eine Menüoption zum **Erstellen eines Formularverarbeitungsmodells** in SharePoint-Dokumentbibliotheken verfügbar, in denen es aktiviert ist.
 
     Für **Welche SharePoint-Bibliotheken sollen die Option zum Erstellen eines Formularverarbeitungsmodells anzeigen** können Sie Folgendes auswählen:</br>
      - **Bibliotheken in allen SharePoint-Websites**, damit die Option für alle SharePoint-Bibliotheken in Ihrer Organisation verfügbar gemacht wird.</br>
      - **Bibliotheken in ausgewählten SharePoint-Websites**. Wählen Sie dann die Websites aus, auf denen Sie die Option verfügbar machen möchten, oder laden Sie eine Liste mit bis zu 50 Websites hoch.</br>
      - **Keine SharePoint-Bibliotheken**, wenn Sie die Option nicht auf Websites verfügbar machen möchten (Sie können dies nach der Einrichtung ändern).

   > [!div class="mx-imgBorder"]
   > ![Konfigurieren der Websiteoptionen für die Formularverarbeitung](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Wenn Sie eine Website entfernen, nachdem sie hinzugefügt wurde, hat dies keine Auswirkung auf vorhandene Modelle, die auf die Bibliotheken auf dieser Website angewendet werden, oder die Möglichkeit, Dokumentverständnismodelle auf eine Bibliothek anzuwenden. 
    
    Wenn Sie mehrere Power Platform-Umgebungen konfiguriert haben, können Sie wählen, welche Sie für die Formularverarbeitung verwenden möchten. (Diese Option wird nicht angezeigt, wenn Sie nur eine Umgebung konfiguriert haben).

    ![Konfigurieren der Power Platform-Optionen für die Formularverarbeitung](../media/content-understanding/setup-power-platform-env.png)

    Für **Power Platform-Umgebung** können Sie wählen:
    - **Standardumgebung verwenden**, um Ihre standardmäßige Power Platform-Umgebung zu verwenden.
    - **Benutzerdefinierte Umgebung verwenden**, um eine benutzerdefinierte Umgebung zu verwenden. Wählen Sie die zu verwendende Umgebung aus der Liste aus. ([Weitere Informationen zu den Anforderungen für eine benutzerdefinierte Umgebung](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)).

    Klicken Sie auf **Weiter**.

5. Auf der Seite **Inhaltscenter erstellen** können Sie eine Website im SharePoint-Inhaltscenter erstellen, auf der Ihre Benutzer Modelle zum Dokumentverständnis erstellen und verwalten können.

    1. Geben Sie für den **Websitenamen** den Namen ein, den Sie Ihrer Inhaltscenter-Website zuweisen möchten.
    
    1. Die **Websiteadresse** zeigt die URL für Ihre Website basierend auf Ihrer Auswahl für den Websitenamen an. Wenn Sie die Einstellungen ändern möchten, klicken Sie auf **Bearbeiten**.

       > [!div class="mx-imgBorder"]
       > ![Erstellen eines Inhaltscenters](../media/content-understanding/admin-cu-create-cc.png)</br>

       Wählen Sie **Weiter** aus.

6. Auf der Seite **Überprüfen und beenden** können Sie sich die ausgewählte Einstellung ansehen und Änderungen vornehmen. Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Aktivieren** aus.

7. Klicken Sie auf der Bestätigungsseite auf **Fertig**.

8. Sie kehren zur Seite **Inhaltsverständnis automatisieren** zurück. Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen. 

## <a name="assign-licenses"></a>Lizenzen zuweisen

Nachdem Sie SharePoint Syntex konfiguriert haben, müssen Sie Lizenzen für die Benutzer zuweisen, die SharePoint Syntex-Features verwenden werden.

So weisen Sie Lizenzen zu

1. Klicken Sie im Microsoft 365 Admin Center auf **Benutzer** > **Aktive Benutzer**.

2. Wählen Sie die Benutzer aus, denen Sie eine Lizenz zuweisen möchten, und wählen Sie **Produktlizenzen verwalten** aus.

3. Wählen Sie im Dropdownmenü die Option **Apps** aus.

4. Wählen Sie **Apps für SharePoint Syntex anzeigen** aus. Stellen Sie sicher, dass unter **Apps** sowohl **Gemeinsamer Datendienst für SharePoint Syntex**, **SharePoint Syntex** wie auch **SharePoint Syntex – SPO-Typ** ausgewählt sind.

    > [!div class="mx-imgBorder"]
    > ![SharePoint Syntex-Lizenzen im Microsoft 365 Admin Center](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Klicken Sie auf **Änderungen speichern**.

## <a name="see-also"></a>Weitere Informationen:

[Übersicht über das Formularverarbeitungsmodell](/ai-builder/form-processing-model-overview)

[Schrittweise Anleitung zum Erstellen eines Modells für das Dokumentverständnis (Video)](https://www.youtube.com/watch?v=DymSHObD-bg)

[Erstellen und Verwalten von Umgebungen im Power Platform Admin Center](/power-platform/admin/create-environment)
