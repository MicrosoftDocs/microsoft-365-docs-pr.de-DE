---
title: Einrichten eines Connectors zum Archivieren von WeChat-Daten in Microsoft 365
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
description: Einrichten und Verwenden eines Connectors im Microsoft 365 Compliance Center zum Importieren und Archivieren von WeChat-Daten in Microsoft 365.
ms.openlocfilehash: 3ee858cd09c1b6c7bd29dc5e2162753df9f5544a
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861632"
---
# <a name="set-up-a-connector-to-archive-wechat-data-preview"></a>Einrichten eines Connectors zum Archivieren von WeChat-Daten (Vorschau)

Verwenden Sie den TeleMessage-Connector im Microsoft 365 Compliance Center, um WeChat- und WeCom-Anrufe, Chats, Anlagen, Dateien und zurückgerufene Nachrichten zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, wird eine Verbindung mit dem TeleMessage-Konto Ihrer Organisation hergestellt und die mobile Kommunikation von Mitarbeitern mithilfe des TeleMessage WeChat-Archivs in Postfächer in Microsoft 365 importiert.

Nachdem WeChat Archiver Connector-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliance-Features wie Beweissicherung für juristische Zwecke, eDiscovery, In-Place Archivierung, Überwachung, Kommunikationscompliance und Microsoft 365 Aufbewahrungsrichtlinien auf WeChat-Kommunikationsdaten anwenden. Sie können z. B. die WeChat-Kommunikation mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die WeChat Archiver-Connectordaten enthält, einem Verwahrer in einem Advanced eDiscovery Fall zuordnen. Die Verwendung eines WeChat Archiver-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Corporate Governance-Bestimmungen und behördlichen Richtlinien zu gewährleisten.

## <a name="overview-of-archiving-wechat-communication-data"></a>Übersicht über die Archivierung von WeChat-Kommunikationsdaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von WeChat-Kommunikationsdaten in Microsoft 365 erläutert.

![Archivierungsworkflow für WeChat-Archivdaten](../media/WeChatConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage zusammen, um einen WeChat Archiver-Connector einzurichten.

2. In Echtzeit werden die WeChat-Daten Ihrer Organisation auf die TeleMessage-Website kopiert.

3. Der WeChat Archiver-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der TeleMessage-Website her und überträgt die E-Mail-Nachrichten aus den letzten 24 Stunden in einen sicheren Azure Storage Bereich in der Microsoft Cloud.

4. Der Connector importiert die Mobilen Kommunikationselemente in das Postfach eines bestimmten Benutzers. Ein neuer Ordner mit dem Namen "WeChat Archiver" wird im Postfach des bestimmten Benutzers erstellt, und die Elemente werden in das Postfach importiert. Der Connector verwendet die Zuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft des Benutzers.* Jede E-Mail-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der E-Mail-Nachricht aufgefüllt wird. Zusätzlich zur automatischen Benutzerzuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft* des Benutzers können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei sollte die Mobiltelefonnummer des Benutzers und die entsprechende Microsoft 365 Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird der Connector für jedes E-Mail-Element zuerst die benutzerdefinierte Zuordnungsdatei betrachten. Wenn kein gültiger Microsoft 365 Benutzer gefunden wird, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die E-Mail-Adresseigenschaft des Benutzers des E-Mail-Elements. Wenn der Connector keinen gültigen Microsoft 365 Benutzer in der benutzerdefinierten Zuordnungsdatei oder in der *E-Mail-Adresseigenschaft* des E-Mail-Elements des Benutzers findet, wird das Element nicht importiert.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

- Arbeiten Sie mit TeleMessage, um einen WeChat-Archivconnector einzurichten. Weitere Informationen finden Sie unter [Aktivieren des TeleMessage WeChat-Archivers für Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/).

- Richten Sie einen TeleMessage-Connector für Microsoft 365 ein, und rufen Sie ein gültiges Unternehmensverwaltungskonto ab. Weitere Informationen finden Sie unter [Order Microsoft 365 Mobile Archiving](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/).

- Registrieren Sie alle Benutzer, für die die WeChat-Archivierung erforderlich ist, im TeleMessage-Konto mit derselben E-Mail-Adresse, die für das Microsoft 365 Konto des Benutzers verwendet wird.

- Sie müssen die Tencent WeCom-App auf den Mobiltelefonen von Benutzern in Ihrer Organisation installieren und aktivieren. Mit der WeCom-App können Benutzer mit anderen WeChat- und WeCom-Benutzern kommunizieren und chatten.

- Dem Benutzer, der im Microsoft 365 Compliance Center einen WeChat Archiver-Connector erstellt, muss die Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Dies ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Dieser Datenkonnektor ist in GCC Umgebungen in der Microsoft 365 US Government-Cloud verfügbar. Drittanbieteranwendungen und -dienste umfassen möglicherweise das Speichern, Übertragen und Verarbeiten der Kundendaten Ihrer Organisation auf Drittanbietersystemen, die sich außerhalb der Microsoft 365-Infrastruktur befinden und daher nicht unter die Verpflichtungen zur Einhaltung der Microsoft 365 und zum Datenschutz fallen. Microsoft macht keine Darstellung, dass die Verwendung dieses Produkts zum Herstellen einer Verbindung mit Drittanbieteranwendungen impliziert, dass diese Drittanbieteranwendungen FEDRAMP-konform sind.

## <a name="create-a-wechat-archiver-connector"></a>Erstellen eines WeChat Archiver-Connectors

Führen Sie die Schritte in diesem Abschnitt aus, um einen WeChat Archiver-Connector im Microsoft 365 Compliance Center zu erstellen. Der Connector verwendet die von Ihnen angegebenen Informationen, um eine Verbindung mit der TeleMessage-Website herzustellen und WeChat-Kommunikationsdaten an die entsprechenden Benutzerpostfächer in Microsoft 365 zu übertragen.

1. Wechseln Sie zu <https://compliance.microsoft.com> "Datenconnectors WeChat Archiver", und klicken Sie dann auf **"Datenkonnektoren".**  >  

2. Klicken Sie auf der Seite **"WeChat** Archiver-Produktbeschreibung" auf **"Connector hinzufügen".**

3. Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie auf der Seite **"Bei TeleMessage anmelden"** unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **"Weiter".**

    - **Benutzername:** Ihr TeleMessage-Benutzername.

    - **Kennwort:** Ihr TeleMessage-Kennwort.

5. Nachdem der Connector erstellt wurde, können Sie das Popupfenster schließen und zur nächsten Seite wechseln.

6. Aktivieren Sie auf der Seite **"Benutzerzuordnung"** die automatische Benutzerzuordnung. Sie können auch eine benutzerdefinierte BENUTZERzuordnungs-CSV-Datei hochladen.

7. Klicken Sie auf **"Weiter",** überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **"Fertig stellen",** um den Connector zu erstellen.

8. Wechseln Sie zur Registerkarte **Connectors** auf der Seite **"Datenconnectors",** um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
