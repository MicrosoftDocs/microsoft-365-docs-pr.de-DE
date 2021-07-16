---
title: Einrichten eines Connectors zum Archivieren von LivePerson Conversational Cloud-Daten in Microsoft 365
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
description: Erfahren Sie, wie Sie einen 17a-4 LivePerson Conversational Cloud DataParser-Connector einrichten und verwenden, um LivePerson Conversational Cloud-Daten in Microsoft 365 zu importieren und zu archivieren.
ms.openlocfilehash: 70b8e8bd1c8c411894a90e0f919581b3faf58cae
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454457"
---
# <a name="set-up-a-connector-to-archive-liveperson-conversational-cloud-data"></a>Einrichten eines Connectors zum Archivieren von LivePerson Conversational Cloud-Daten

Verwenden Sie die [LivePerson Conversational Cloud DataParser](https://www.17a-4.com/liveperson-dataparser/) von 17a-4 LLC, um Daten aus der LivePerson Conversational Cloud in Benutzerpostfächer in Ihrer Microsoft 365 Organisation zu importieren und zu archivieren. Der DataParser enthält einen LivePerson Conversational Cloud-Connector, der so konfiguriert ist, dass Elemente aus einer Datenquelle eines Drittanbieters erfasst und diese Elemente in Microsoft 365 importiert werden. Der LivePerson Conversational Cloud DataParser-Connector konvertiert Daten in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in Benutzerpostfächer in Microsoft 365.

Nachdem Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung für juristische Zwecke, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Kommunikationscompliance anwenden. Die Verwendung eines LivePerson Conversational Cloud Connector zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Behörden- und Behördlichen Richtlinien zu halten.

## <a name="overview-of-archiving-liveperson-conversational-cloud-data"></a>Übersicht über die Archivierung von LivePerson Conversational Cloud-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Datenkonnektors zum Archivieren von LivePerson Conversational Cloud-Daten in Microsoft 365 erläutert.

![Archivierungsworkflow für LivePerson Conversational Cloud-Daten von 17a-4](../media/LiveEngageDataParserConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit 17a-4 zusammen, um die LivePerson Conversational Cloud DataParser einzurichten und zu konfigurieren.

2. In regelmäßigen Abständen werden LivePerson Conversational Cloud-Elemente von DataParser gesammelt. Der DataParser konvertiert auch den Inhalt einer Nachricht in ein E-Mail-Nachrichtenformat.

3. Der LivePerson Conversational Cloud DataParser-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt eine Verbindung mit DataParser her und überträgt die Nachrichten an einen sicheren Azure Storage Ort in der Microsoft-Cloud.

4. Ein Unterordner im Ordner "Posteingang" mit dem Namen **"LivePerson Conversational Cloud DataParser"** wird in den Benutzerpostfächern erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der *E-Mail-Eigenschaft,* in welches Postfach Elemente importiert werden sollen. Jedes Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers aufgefüllt wird.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

- Erstellen Sie ein DataParser-Konto für Microsoft Connectors. Wenden Sie sich hierzu an [17a-4 LLC.](https://www.17a-4.com/contact/) Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den LivePerson Conversational Cloud DataParser-Connector in Schritt 1 erstellt (und in Schritt 3 abschließt), muss der Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Diese Rolle ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-a-liveperson-conversational-cloud-dataparser-connector"></a>Schritt 1: Einrichten eines LivePerson Conversational Cloud DataParser-Connectors

Der erste Schritt besteht darin, auf die Seite "Datenconnectors" im Microsoft 365 Compliance Center zuzugreifen und einen 17a-4-Connector für LivePerson Conversational Cloud-Daten zu erstellen.

1. Wechseln Sie zu <https://compliance.microsoft.com> und klicken Sie dann auf **Datenconnectors**  >  **LivePerson Conversational Cloud DataParser**.

2. Klicken Sie auf der Seite **"LivePerson Conversational Cloud DataParser"** auf **"Connector hinzufügen".**

3. Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **"Weiter".**

5. Melden Sie sich bei Ihrem 17a-4-Konto an, und führen Sie die Schritte im Assistenten zum Verbinden von LivePerson Conversational Cloud DataParser aus.

## <a name="step-2-configure-the-liveperson-conversational-cloud-dataparser-connector"></a>Schritt 2: Konfigurieren des LivePerson Conversational Cloud DataParser-Connectors

Arbeiten Sie mit dem 17a-4-Support, um den LivePerson Conversational Cloud DataParser-Connector zu konfigurieren.

## <a name="step-3-map-users"></a>Schritt 3: Zuordnen von Benutzern

Der LivePerson Conversational Cloud DataParser-Connector ordnen Benutzer automatisch ihren Microsoft 365 E-Mail-Adressen zu, bevor Daten in Microsoft 365 importiert werden.

## <a name="step-4-monitor-the-liveperson-conversational-cloud-dataparser-connector"></a>Schritt 4: Überwachen des LivePerson Conversational Cloud DataParser-Connectors

Nachdem Sie einen LivePerson Conversational Cloud DataParser-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie in <https://compliance.microsoft.com> der linken Navigationsleiste zu "Datenconnectors", und klicken Sie auf **"Datenconnectors".**

2. Klicken Sie auf die Registerkarte **Connectors,** und wählen Sie dann den LivePerson Conversational Cloud DataParser-Connector aus, den Sie erstellt haben, um die Flyoutseite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

3. Klicken Sie unter **Connectorstatus mit Quelle** auf den Link **"Protokoll herunterladen",** um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
