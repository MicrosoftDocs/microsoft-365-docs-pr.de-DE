---
title: Einrichten eines Connectors zum Archivieren von XSLT/XML-Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von XSLT/XML-Daten aus Demanet in Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, damit Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 097b523b6a1909f3f9575302fe11ad61a7558472
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921725"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>Einrichten eines Connectors zum Archivieren von XSLT/XML-Daten

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center, um Daten aus der Webseitenquelle in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Mit Einem [XSLT/XML-Connector](https://globanet.com/xslt-xml) bietet Ihnen Dies ermöglicht die schnelle Entwicklung von Dateien, die mithilfe von XSLT (Extensible Stylesheet Language Transformations) erstellt wurden, um XML-Dateien in andere Dateiformate (z. B. HTML oder Text) zu transformieren, die in Microsoft 365 importiert werden können. Der Connector konvertiert den Inhalt eines Elements aus der XSLT/XML-Quelle in ein E-Mail-Nachrichtenformat und importiert das konvertierte Element dann in Microsoft 365-Postfächer.

Nachdem XSLT-/XML-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. Das Aufbewahrungsverfahren für Rechtsstreitigkeiten, eDiscovery und Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anwenden. Die Verwendung eines XSLT/XML-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Richtlinien von Behörden und Behörden einhalten kann.

## <a name="overview-of-archiving-xsltxml-data"></a>Übersicht über die Archivierung von XSLT-/XML-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von XSLT/XML-Quelldaten in Microsoft 365 erläutert.

![Archivierungsworkflow für XSLT/XML-Daten](../media/XSLT-XMLConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit der XSLT/XML-Quelle zusammen, um eine XSLT/XML-Website einrichten und konfigurieren zu können.

2. Einmal alle 24 Stunden werden Chatnachrichten aus der XSLT/XML-Quelle auf die Website "Globanet Merge1" kopiert. Der Connector konvertiert den Inhalt auch in ein E-Mail-Nachrichtenformat.

3. Der XSLT/XML-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Website "Globenet Merge1" bereit und überträgt die Nachrichten an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Nachrichtenelemente mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung in die Postfächer bestimmter Benutzer, wie in Schritt 3 beschrieben. In den Benutzerpostfächern wird ein neuer Unterordner im Posteingangsordner mit dem Namen **XSLT/XML** erstellt, und die Nachrichtenelemente werden in diesen Ordner importiert. Der Connector verwendet dazu den Wert der *Email-Eigenschaft.* Jede Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der Nachricht gefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für das Merge1-Konto von "GlobeNet Merge1" für Microsoft-Connectors. Wenden Sie sich zum Erstellen dieses Kontos an [den Kundensupport von "Globenet".](https://globanet.com/contact-us/) Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den XSLT/XML-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen) muss der Rolle Postfachimportexport in Exchange Online zugewiesen werden. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Diese Rolle ist standardmäßig nicht einer Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-an-xsltxml-connector"></a>Schritt 1: Einrichten eines XSLT/XML-Connectors

Der erste Schritt besteht im Zugriff auf die **Datenconnectors** im Microsoft 365 Compliance Center und dem Erstellen eines Connectors für XSLT/XML-Daten.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors**  >  **XSLT/XML**.

2. Klicken Sie **auf der Seite XSLT/XML-Produktbeschreibung** auf **Neuen Connector hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-an-xsltxml-connector"></a>Schritt 2: Konfigurieren eines XSLT/XML-Connectors

Der zweite Schritt besteht im Konfigurieren des XSLT/XML-Connectors auf dem Merge1-Standort. Weitere Informationen zum Konfigurieren des XSLT/XML-Connectors auf dem Standort "Merge1" finden Sie unter [Merge1-Benutzerhandbuch für Drittanbieterconnectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf).

Nachdem Sie auf **& Beenden** klicken, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

1. Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung im Microsoft 365 Compliance Center abzuschließen:

2. Aktivieren Sie auf der Seite **XSLT/XML-Benutzer zu Microsoft 365-Benutzern** zuordnen die automatische Benutzerzuordnung. Die XSLT/XML-Elemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

3. Klicken **Sie auf Weiter,** überprüfen  Sie Ihre Einstellungen, und wechseln Sie zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-xsltxml-connector"></a>Schritt 4: Überwachen des XSLT/XML-Connectors

Nachdem Sie den XSLT/XML-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie auf **die** Registerkarte Connectors, und wählen Sie dann **den XSLT/XML-Connector** aus, um die Flyoutseite anzeigen zu können. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.