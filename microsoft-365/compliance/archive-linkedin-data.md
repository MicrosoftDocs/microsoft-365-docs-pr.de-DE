---
title: Einrichten eines Connectors zum Archivieren von LinkedIn Daten in Office 365 (Vorschau)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Administratoren können einen systemeigenen Connector zum Importieren von Daten von einer LinkedIn Unternehmensseite in Office 365 einrichten. Auf diese Weise können Sie Daten aus Drittanbieter-Datenquellen in Office 365 archivieren, sodass Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Kompatibilität der drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: bd11102a15396132cb192d8b0a4cc9a0dfca5645
ms.sourcegitcommit: 7f26840a4330b0fd29807ec091c6915d283b3dd2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615625"
---
# <a name="set-up-a-connector-to-archive-linkedin-data-in-office-365-preview"></a>Einrichten eines Connectors zum Archivieren von LinkedIn Daten in Office 365 (Vorschau)

Das Feature "Connector" zum Archivieren von Daten aus LinkedIn Unternehmensseiten in Office 365 befindet sich in der Vorschau.

Verwenden Sie einen systemeigenen Connector im Security #a0 Compliance Center in Office 365, um Daten aus LinkedIn Unternehmensseiten zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, wird er alle 24 Stunden mit dem Konto für die bestimmte Seite des LinkedIn Unternehmens verbunden. Der Connector konvertiert die Nachrichten, die auf die Unternehmensseite gesendet werden, in eine e-Mail-Nachricht und importiert diese Elemente dann in ein Postfach in Office 365.

Nachdem die Daten der LinkedIn Unternehmensseite in einem Postfach gespeichert wurden, können Sie Office 365 Compliance-Features wie Beweissicherungsverfahren, Inhaltssuche, in-situ-Archivierung, Überwachung und Office 365-Aufbewahrungsrichtlinien auf LinkedIn-Daten anwenden. Sie können beispielsweise mithilfe der Inhaltssuche nach diesen Elementen suchen oder das Speicher Postfach einer Depotbank in einem erweiterten eDiscovery-Fall zuordnen. Das Erstellen eines Connectors zum Importieren und Archivieren von LinkedIn-Daten in Office 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="before-you--begin"></a>Bevor Sie beginnen

- Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um dieser Anforderung zuzustimmen, gehen Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), melden Sie sich mit den Anmeldeinformationen eines Office 365 globalen Administrators an, und nehmen Sie dann die Anforderung an.

- Dem Benutzer, der einen Unternehmensseiten-Konnektor für LinkedIn erstellt, muss in Exchange Online die Rolle "Post Fach Import/-Export" zugewiesen sein. Diese Rolle ist erforderlich, um im Security #a0 Compliance Center auf die Seite **Archivieren von drittanbieterdaten** zuzugreifen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Sie müssen über die Anmeldeinformationen (e-Mail-Adresse oder Telefonnummer und das Kennwort) eines LinkedIn-Benutzerkontos verfügen, das ein Administratorkonto für die Seite LinkedIn Company ist, die Sie archivieren möchten. Sie verwenden diese Anmeldeinformationen, um sich beim Einrichten des Connectors bei LinkedIn anzumelden.

## <a name="create-a-linkedin-connector"></a>Erstellen eines LinkedIn Connectors

1. Wechseln Sie <https://protection.office.com> zu und wählen Sie dann **Data Governance \> Import** aus, und wählen Sie dann **Archivieren von drittanbieterdaten**aus.

2. Wählen Sie auf der Seite **drittanbieterdaten archivieren** die Option **Connector hinzufügen**aus, und wählen Sie dann **LinkedIn**aus.

3. Wählen Sie auf der Seite **Nutzungsbedingungen** die Option **akzeptieren**aus.

4. Wählen Sie auf der Seite **mit LinkedIn anmelden** die Option **Anmelden bei LinkedIn**aus.

   Die LinkedIn-Anmeldeseite wird angezeigt.

   ![LinkedIn Anmeldeseite](media/LinkedInSigninPage.png)

5. Geben Sie auf der Seite LinkedIn anmelden die e-Mail-Adresse (oder Telefonnummer) und das Kennwort für das LinkedIn-Konto ein, das der Unternehmensseite zugeordnet ist, die Sie archivieren möchten, und wählen Sie dann **Anmelden**aus.

   Eine Assistentenseite wird mit einer Liste aller LinkedIn Unternehmensseiten angezeigt, die dem Konto zugeordnet sind, mit dem Sie sich angemeldet haben. Ein Connector kann nur für eine Unternehmensseite konfiguriert werden. Wenn Ihre Organisation über mehrere LinkedIn Unternehmensseiten verfügt, müssen Sie für jeden eine Verbindung erstellen.

   ![Eine Seite mit einer Liste von LinkedIn Unternehmensseiten wird angezeigt](media/LinkedInSelectCompanyPage.png)

6. Wählen Sie die Unternehmensseite aus, von der Sie Elemente archivieren möchten, und klicken Sie dann auf **weiter**.

7. Auf der Seite **Filter festlegen** können Sie einen Filter anwenden, um Elemente anfänglich zu importieren, die ein bestimmtes Alter aufweisen. Wählen Sie ein Alter aus, und wählen Sie dann **weiter**aus.

8. Geben Sie auf der Seite **Speicherkonto festlegen** die e-Mail-Adresse eines Office 365 Postfachs ein, in das die LinkedIn Elemente importiert werden sollen, und wählen Sie dann **weiter**aus. Elemente werden in den Ordner Posteingang in diesem Postfach importiert.

9. Überprüfen Sie die Connectoreinstellungen, und wählen Sie dann **Speichern** aus, um das Connector-Setup abzuschließen.

Nachdem Sie den Connector erstellt haben, können Sie zur Seite **Archivieren von drittanbieterdaten** zurückkehren (Wählen Sie bei Bedarf **Aktualisieren** aus, um die Liste der Connectors zu aktualisieren), um einen neuen Connector anzuzeigen. Der Wert in der Spalte **Status** **wartet auf den Start**. Es dauert bis zu 24 Stunden, bis der erste Importvorgang gestartet wurde. Nachdem der Connector zum ersten Mal ausgeführt und die LinkedIn-Elemente importiert hat, wird der Connector alle 24 Stunden ausgeführt und importiert alle neuen Elemente, die in den vorherigen 24 Stunden auf der Seite "LinkedIn Company" erstellt wurden.

Um weitere Details anzuzeigen, wählen Sie den Konnektor in der Liste auf der Datenseite des **Archivs von Drittanbietern** aus, um die Flyout-Seite anzuzeigen. Unter **Status**gibt der angezeigte Datumsbereich den Altersfilter an, der beim Erstellen des Konnektors ausgewählt wurde. 

## <a name="more-information"></a>Weitere Informationen

- LinkedIn-Elemente werden in den Ordner Posteingang im Speicher Postfach in Office 365 importiert. Sie werden als e-Mail-Nachrichten angezeigt. Der Anzeigename des Absenders der Nachricht ist der Name der LinkedIn Company-Seite. Die tatsächliche e-Mail-Adresse des Absenders ist die e-Mail-Adresse des Speicher Postfachs. Der Name der Unternehmensseite wird auch der Betreffzeile vorab angefügt. 

- Aufgrund des vorherigen Verhaltens können Sie die `from` oder `subject` e-Mail-Eigenschaften durchsuchen, wenn Sie ein Microsoft eDiscovery-Tool zum Durchsuchen von LinkedIn-Elementen verwenden, die in Office 365 archiviert werden. Wenn beispielsweise der Name der Unternehmensseite "Contoso Company page" lautet, können Sie eine der folgenden *Eigenschaft: Wert-* Paare in der Stichwort Suchabfrage verwenden:
   
   > von: "Contoso Company page"

    Oder:

   > Betreff: "Contoso Company page"

- Damit Sie das Auffinden oder Verwalten von in Office 365 importierten LinkedIn-Elementen vereinfachen können, kann der Besitzer des Speicher Postfachs (oder jeder, dem die Berechtigung "FullAccess" zugewiesen ist) eine Posteingangsregel einrichten, um die Elemente von einer LinkedIn Unternehmensseite in einen bestimmten Ordner zu verschieben. Dies ist hilfreich, wenn das Speicher Postfach zum Archivieren von Elementen verwendet wird, die aus anderen Datenquellen von Drittanbietern importiert wurden. Sie können beispielsweise eine Posteingangsregel erstellen, mit der alle Elemente, die den Namen einer bestimmten LinkedIn Unternehmensseite enthalten, im Feld Betreff in einen bestimmten Ordner verschoben werden.