---
title: Einrichten eines Connectors zum Archivieren von RingCentral-Daten in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Administratoren können einen Connector zum Importieren und Archivieren von RingCentral-Daten aus Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren. Nachdem Sie diese Daten archiviert haben, können Sie Compliance-Features wie gesetzliche Aufbewahrung, eDiscovery und Aufbewahrungsrichtlinien verwenden, um Daten von Drittanbietern zu verwalten.
ms.openlocfilehash: b5e98df50b0610c9fb583a8521c7a6d6fdb48e44
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276857"
---
# <a name="set-up-a-connector-to-archive-ringcentral-data-preview"></a>Einrichten eines Connectors zum Archivieren von RingCentral-Daten (Vorschau)

Verwenden Sie einen Connectors in der Microsoft 365 Compliance Center, um Daten von der RingCentral-Plattform in Benutzerpostfächer in Ihrer Microsoft 365 Organisation zu importieren und zu archivieren. Stellt einen [RingCentral-Connector](https://www.veritas.com/insights/merge1/ringcentral) bereit, der so konfiguriert ist, dass Elemente aus der Datenquelle eines Drittanbieters erfasst und in Microsoft 365 importiert werden. Der Connector konvertiert Inhalte wie Chats, Anlagen, Aufgaben, Notizen und Beiträge von RingCentral in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in die Benutzerpostfächer in Microsoft 365.

Nachdem RingCentral-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung für juristische Zwecke, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anwenden. Die Verwendung eines RingCentral-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Behörden- und Behördlichen Richtlinien zu halten.

## <a name="overview-of-archiving-ringcentral-data"></a>Übersicht über die Archivierung von RingCentral-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der RingCentral-Daten in Microsoft 365 erläutert.

![Archivierungsworkflow für RingCentral-Daten](../media/RingCentralConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit RingCentral zusammen, um eine RingCentral-Website einzurichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden RingCentral-Elemente auf die Website Seriendruck1 kopiert. Der Connector konvertiert auch RingCentral-Elemente in ein E-Mail-Nachrichtenformat.

3. Der RingCentral-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der Website "Merge1" her und überträgt den RingCentral-Inhalt an einen sicheren Azure Storage Standort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *E-Mail-Eigenschaft* der automatischen Benutzerzuordnung, wie in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschrieben. Ein Unterordner im Ordner "Posteingang" mit dem Namen **"RingCentral"** wird in den Benutzerpostfächern erstellt, und Elemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der *E-Mail-Eigenschaft,* in welches Postfach Elemente importiert werden sollen. Jedes RingCentral-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

- Erstellen Sie ein Merge1-Konto für Microsoft-Connectors. Um dieses Konto zu erstellen, wenden Sie sich an [den Kundensupport.](https://www.veritas.com/form/requestacall/ms-connectors-contact) Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Erstellen Sie eine RingCentral-Anwendung, um Daten aus Ihrem RingCentral-Konto abzurufen. Schritt-für-Schritt-Anweisungen zum Erstellen der Anwendung finden Sie im [Benutzerhandbuch für Merge1-Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)von Drittanbietern.

- Der Benutzer, der den RingCentral-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen hat), muss der Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Diese Rolle ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-ringcentral-connector"></a>Schritt 1: Einrichten des RingCentral-Connectors

Der erste Schritt besteht darin, auf die **Seite "Datenkonnektoren"** im Microsoft 365 Compliance Center zuzugreifen und einen Connector für RingCentral-Daten zu erstellen.

1. Wechseln Sie zu <https://compliance.microsoft.com> "Data Connectors RingCentral", und klicken Sie dann auf **"Datenkonnektoren".**  >  

2. Klicken Sie auf der Seite **"RingCentral-Produktbeschreibung"** auf **"Connector hinzufügen".**

3. Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **"Weiter".**

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-ringcentral-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des RingCentral auf der Website "Merge1"

Der zweite Schritt besteht darin, den RingCentral-Connector auf dem Standort "Merge1" zu konfigurieren. Informationen zum Konfigurieren des RingCentral-Connectors finden Sie im Benutzerhandbuch für [Merge1-Connectors von Drittanbietern.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)

Nachdem Sie auf **"Speichern & Fertig stellen"** geklickt haben, wird die **Seite "Benutzerzuordnung"** im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und die Connectoreinrichtung im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der **Map RingCentral-Benutzer Microsoft 365 Benutzerseite** die automatische Benutzerzuordnung. Die RingCentral-Elemente enthalten eine Eigenschaft namens *"Email",* die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365 Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf **"Weiter",** überprüfen Sie Ihre Einstellungen, und wechseln Sie dann zur Seite **"Datenconnectors",** um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-ringcentral-connector"></a>Schritt 4: Überwachen des RingCentral-Connectors

Nachdem Sie den RingCentral-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie in <https://compliance.microsoft.com/> der linken Navigationsleiste zu "Datenconnectors", und klicken Sie auf **"Datenconnectors".**

2. Klicken Sie auf die Registerkarte **Connectors,** und wählen Sie dann den **RingCentral-Connector** aus, um die Flyoutseite anzuzeigen, die die Eigenschaften und Informationen zum Verbinder enthält.

3. Klicken Sie unter **Connectorstatus mit Quelle** auf den Link **"Protokoll herunterladen",** um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
