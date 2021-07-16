---
title: Einrichten eines Connectors zum Archivieren von ICE-Verbinden Chatdaten in Microsoft 365
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
description: Erfahren Sie, wie Sie einen 17a-4 ICE Verbinden Chat DataParser-Connector einrichten und verwenden, um ICE-Verbinden Chatdaten in Microsoft 365 zu importieren und zu archivieren.
ms.openlocfilehash: 0aac5c701f122eaf99497635281ebc07d835fc2e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454481"
---
# <a name="set-up-a-connector-to-archive-ice-connect-chat-data"></a>Einrichten eines Connectors zum Archivieren von ICE-Verbinden Chatdaten

Verwenden Sie ice [DataParser](https://www.17a-4.com/ice-dataparser/) von 17a-4 LLC, um Daten aus ICE Verbinden Chat in Benutzerpostfächer in Ihrer Microsoft 365 Organisation zu importieren und zu archivieren. Der DataParser enthält einen ICE-Chat-Connector, der so konfiguriert ist, dass Elemente aus einer Datenquelle eines Drittanbieters erfasst und in Microsoft 365 importiert werden. Der ICE DataParser-Connector konvertiert ICE Verbinden Chatdaten in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in Benutzerpostfächer in Microsoft 365.

Nachdem ICE Verbinden Chatdaten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung für juristische Zwecke, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Kommunikationscompliance anwenden. Die Verwendung eines ICE DataParser-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Behörden- und Behördlichen Richtlinien zu halten.

## <a name="overview-of-archiving-ice-chat-data"></a>Übersicht über die Archivierung von ICE-Chatdaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Datenkonnektors zum Archivieren von ICE Verbinden Chatdaten in Microsoft 365 erläutert.

![Archivierungsworkflow für ICE Verbinden Chatdaten von 17a-4](../media/ICEChatDataParserConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit 17a-4 zusammen, um ice DataParser einzurichten und zu konfigurieren.

2. In regelmäßigen Abständen werden ICE-Verbinden Chatelemente von DataParser gesammelt. Der DataParser konvertiert auch den Inhalt einer Nachricht in ein E-Mail-Nachrichtenformat.

3. Der ICE DataParser-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt eine Verbindung mit DataParser her und überträgt die Nachrichten an einen sicheren Azure Storage Standort in der Microsoft-Cloud.

4. Ein Unterordner im Posteingangsordner mit dem Namen **ICE DataParser** wird in den Benutzerpostfächern erstellt, und die ICE-Verbinden Chatelemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der *E-Mail-Eigenschaft,* in welches Postfach Elemente importiert werden sollen. Jedes ICE Verbinden Chat-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers aufgefüllt wird.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

- Erstellen Sie ein DataParser-Konto für Microsoft Connectors. Wenden Sie sich hierzu an [17a-4 LLC.](https://www.17a-4.com/contact/) Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den ICE DataParser-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen hat), muss der Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Diese Rolle ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-an-ice-dataparser-connector"></a>Schritt 1: Einrichten eines ICE DataParser-Connectors

Der erste Schritt besteht darin, auf die Seite "Datenconnectors" im Microsoft 365 Compliance Center zuzugreifen und einen 17a-4-Connector für ICE-Verbinden Chatdaten zu erstellen.

1. Wechseln <https://compliance.microsoft.com> Sie zu **data connectors**  >  **ICE DataParser,** und klicken Sie dann darauf.

2. Klicken Sie auf der **Ice DataParser-Produktbeschreibungsseite** auf **Connector hinzufügen.**

3. Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **"Weiter".**

5. Melden Sie sich bei Ihrem 17a-4-Konto an, und führen Sie die Schritte im ICE DataParser-Verbindungsassistenten aus.

## <a name="step-2-configure-the-ice-dataparser-connector"></a>Schritt 2: Konfigurieren des ICE DataParser-Connectors

Arbeiten Sie mit der 17a-4-Unterstützung, um den ICE DataParser-Connector zu konfigurieren.

## <a name="step-3-map-users"></a>Schritt 3: Zuordnen von Benutzern

Der ICE DataParser-Connector ordnen Benutzer automatisch ihren Microsoft 365 E-Mail-Adressen zu, bevor Daten in Microsoft 365 importiert werden.

## <a name="step-4-monitor-the-ice-dataparser-connector"></a>Schritt 4: Überwachen des ICE DataParser-Connectors

Nachdem Sie einen ICE DataParser-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie in <https://compliance.microsoft.com> der linken Navigationsleiste zu "Datenconnectors", und klicken Sie auf **"Datenconnectors".**

2. Klicken Sie auf die Registerkarte **Connectors,** und wählen Sie dann den ICE DataParser-Connector aus, den Sie erstellt haben, um die Flyoutseite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

3. Klicken Sie unter **Connectorstatus mit Quelle** auf den Link **"Protokoll herunterladen",** um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
