---
title: Einrichten eines Connectors zum Archivieren Skype for Business Daten in Microsoft 365
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
description: Erfahren Sie, wie Sie einen Connector in der Microsoft 365 Compliance Center einrichten und verwenden, um Daten aus Skype for Business in Microsoft 365 zu importieren und zu archivieren.
ms.openlocfilehash: 4a66ee19530860bd482168297a8c935153442fee
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339454"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data"></a>Einrichten eines Connectors zum Archivieren Skype for Business Daten

Verwenden Sie einen Connectors in der Microsoft 365 Compliance Center, um Daten aus der Skype for Business Plattform in Benutzerpostfächer in Ihrer Microsoft 365 Organisation zu importieren und zu archivieren. Stellt einen [Skype for Business](https://www.veritas.com/en/au/insights/merge1/skype-for-business) Connector bereit, der so konfiguriert ist, dass Elemente aus der Datenquelle eines Drittanbieters (in regelmäßigen Abständen) erfasst und in Microsoft 365 importiert werden. Der Connector konvertiert den Inhalt, z. B. Nachrichten zwischen Benutzern, beständigen Chats und Konferenznachrichten, aus Skype for Business in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem Skype for Business Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung für juristische Zwecke, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anwenden. Die Verwendung eines Skype for Business Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Regierungsrichtlinien und behördlichen Richtlinien zu halten.

## <a name="overview-of-archiving-skype-for-business-data"></a>Übersicht über die Archivierung Skype for Business Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der Skype for Business Daten in Microsoft 365 erläutert.

![Archivierungsworkflow für Skype for Business Daten](../media/SkypeforBusinessConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Skype for Business zusammen, um eine Skype for Business Website einzurichten und zu konfigurieren.

2. Alle 24 Stunden werden Skype for Business Elemente auf die Website Seriendruck1 kopiert. Der Connector konvertiert auch Skype for Business Elemente in ein E-Mail-Nachrichtenformat.

3. Der Skype for Business Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der Website "Seriendruck1" her und überträgt die Skype for Business Inhalte an einen sicheren Azure Storage Standort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *E-Mail-Eigenschaft* der automatischen Benutzerzuordnung, wie in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschrieben. Ein Unterordner im Posteingangsordner mit dem Namen **Skype for Business** wird in den Benutzerpostfächern erstellt, und Elemente werden in diesen Ordner importiert. Der Connector verwendet dazu den Wert der *Email-Eigenschaft.* Jedes Skype for Business Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

- Erstellen Sie ein Merge1-Konto für Microsoft-Connectors. Wenden Sie sich hierzu an [den Kundensupport.](https://www.veritas.com/form/requestacall/ms-connectors-contact.html) Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den Skype for Business Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen hat), muss der Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Diese Rolle ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-skype-for-business-connector"></a>Schritt 1: Einrichten des Skype for Business Connectors

Der erste Schritt besteht darin, auf die **Seite "Datenconnectors"** im Microsoft 365 Compliance Center zuzugreifen und einen Connector für Skype for Business Daten zu erstellen.

1. Wechseln Sie zu <https://compliance.microsoft.com> **Datenconnectors** Skype for Business, und klicken  >  **Sie** darauf.

2. Klicken Sie auf der **Seite Skype for Business** Produktbeschreibung auf **Connector hinzufügen.**

3. Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **"Weiter".**

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren der Skype for Business auf der Merge1-Website

Der zweite Schritt besteht darin, den Skype for Business Connector auf dem Standort "Seriendruck1" zu konfigurieren. Informationen zum Konfigurieren des Skype for Business Connectors finden Sie im [Benutzerhandbuch für Merge1-Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf)von Drittanbietern.

Nachdem Sie auf **"Speichern & Fertig stellen"** geklickt haben, wird die **Benutzerzuordnungsseite** im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und die Connectoreinrichtung im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der Seite **"Karte Skype for Business Benutzer Microsoft 365 Benutzer",** die automatische Benutzerzuordnung. Die Skype for Business Elemente enthalten eine Eigenschaft namens *"E-Mail",* die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365 Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf **"Weiter",** überprüfen Sie Ihre Einstellungen, und wechseln Sie dann zur Seite **"Datenconnectors",** um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-skype-for-business-connector"></a>Schritt 4: Überwachen des Skype for Business Connectors

Nachdem Sie den Skype for Business Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie in <https://compliance.microsoft.com/> der linken Navigationsleiste zu "Datenconnectors", und klicken Sie auf **"Datenconnectors".**

2. Klicken Sie auf die Registerkarte **Connectors,** und wählen Sie dann den **Skype for Business** Connector aus, um die Flyoutseite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

3. Klicken Sie unter **Connectorstatus mit Quelle** auf den Link **"Protokoll herunterladen",** um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
