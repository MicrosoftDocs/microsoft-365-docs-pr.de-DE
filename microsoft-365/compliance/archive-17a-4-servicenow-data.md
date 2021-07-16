---
title: Einrichten eines Connectors zum Archivieren von ServiceNow 17a-4 DataParser-Daten in Microsoft 365
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
description: Erfahren Sie, wie Sie einen 17a-4 ServiceNow DataParser-Connector einrichten und verwenden, um ServiceNow-Daten in Microsoft 365 zu importieren und zu archivieren.
ms.openlocfilehash: a01e075b6cbf400bc3b7dc38950d87443a46f81c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454421"
---
# <a name="set-up-a-connector-to-archive-data-from-servicenow"></a>Einrichten eines Connectors zum Archivieren von Daten aus ServiceNow

Verwenden Sie [ServiceNow DataParser](https://www.17a-4.com/dataparser/) von 17a-4 LLC, um Daten aus ServiceNow in Benutzerpostfächer in Ihrer Microsoft 365 Organisation zu importieren und zu archivieren. The DataParser includes a ServiceNow connector that's configured to capture items from a third-party data source and import those items to Microsoft 365. Der ServiceNow DataParser-Connector konvertiert ServiceNow-Daten in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in Benutzerpostfächer in Microsoft 365.

Nachdem ServiceNow-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung für juristische Zwecke, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Kommunikationscompliance anwenden. Die Verwendung eines ServiceNow-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Behörden- und behördlichen Richtlinien zu halten.

## <a name="overview-of-archiving-servicenow-data"></a>Übersicht über die Archivierung von ServiceNow-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Datenkonnektors zum Archivieren von ServiceNow-Daten in Microsoft 365 erläutert.

![Archivierungsworkflow für ServiceNow-Daten von 17a-4](../media/ServiceNowDataParserConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit 17a-4 zusammen, um ServiceNow DataParser einzurichten und zu konfigurieren.

2. In regelmäßigen Abständen werden ServiceNow-Elemente von DataParser gesammelt. Der DataParser konvertiert auch den Inhalt einer Nachricht in ein E-Mail-Nachrichtenformat.

3. Der ServiceNow DataParser-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt eine Verbindung mit DataParser her und überträgt die Nachrichten an einen sicheren Azure Storage Speicherort in der Microsoft-Cloud.

4. Ein Unterordner im Posteingangsordner mit dem Namen **ServiceNow DataParser** wird in den Benutzerpostfächern erstellt, und die ServiceNow-Elemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der *E-Mail-Eigenschaft,* in welches Postfach Elemente importiert werden sollen. Jedes ServiceNow-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers aufgefüllt wird.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

- Erstellen Sie ein DataParser-Konto für Microsoft Connectors. Wenden Sie sich hierzu an [17a-4 LLC.](https://www.17a-4.com/contact/) Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den ServiceNow DataParser-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen hat), muss der Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Diese Rolle ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-a-servicenow-dataparser-connector"></a>Schritt 1: Einrichten eines ServiceNow DataParser-Connectors

Der erste Schritt besteht darin, auf die Seite "Datenconnectors" im Microsoft 365 Compliance Center zuzugreifen und einen 17a-4-Connector für ServiceNow-Daten zu erstellen.

1. Wechseln Sie zu <https://compliance.microsoft.com> und klicken Sie dann auf **Datenconnectors**  >  **ServiceNow DataParser**.

2. Klicken Sie auf der Seite **"ServiceNow DataParser-Produktbeschreibung"** auf **"Connector hinzufügen".**

3. Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **"Weiter".**

5. Melden Sie sich bei Ihrem 17a-4-Konto an, und führen Sie die Schritte im ServiceNow DataParser-Verbindungs-Assistenten aus.

## <a name="step-2-configure-the-servicenow-dataparser-connector"></a>Schritt 2: Konfigurieren des ServiceNow DataParser-Connectors

Arbeiten Sie mit dem 17a-4-Support, um den ServiceNow DataParser-Connector zu konfigurieren.

## <a name="step-3-map-users"></a>Schritt 3: Zuordnen von Benutzern

Der ServiceNow DataParser-Connector ordnen Benutzer automatisch ihren Microsoft 365 E-Mail-Adressen zu, bevor Daten in Microsoft 365 importiert werden.

## <a name="step-4-monitor-the-servicenow-dataparser-connector"></a>Schritt 4: Überwachen des ServiceNow DataParser-Connectors

Nachdem Sie einen ServiceNow DataParser-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie in <https://compliance.microsoft.com> der linken Navigationsleiste zu "Datenconnectors", und klicken Sie auf **"Datenconnectors".**

2. Klicken Sie auf die Registerkarte **Connectors,** und wählen Sie dann den ServiceNow DataParser-Connector aus, den Sie erstellt haben, um die Flyoutseite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

3. Klicken Sie unter **Connectorstatus mit Quelle** auf den Link **"Protokoll herunterladen",** um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
