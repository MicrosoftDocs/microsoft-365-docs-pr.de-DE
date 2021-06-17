---
title: Konfigurieren des Event Hubs
description: Erfahren Sie, wie Sie Ihren Event Hub konfigurieren
keywords: Event Hub, konfigurieren, Einblicke
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985587"
---
# <a name="configure-your-event-hub"></a>Konfigurieren des Event Hubs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Erfahren Sie, wie Sie Ihren Event Hub so konfigurieren, dass er Ereignisse aus Microsoft 365 Defender erfassen kann.


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a>Einrichten des erforderlichen Ressourcenanbieters im Event Hub-Abonnement


1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
1. Select **Subscriptions { Select the subscription the event hub will be deployed \> ***to***} \> Resource providers**.
1. Stellen Sie sicher, dass der **Microsoft.Insights-Anbieter** registriert ist. Andernfalls registrieren Sie es.

![Abbildung der Ressourcenanbieter in Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a>Einrichten Azure Active Directory App-Registrierung


>! [HINWEIS] Sie müssen über eine Administratorrolle verfügen, oder Azure Active Directory (AAD) muss so festgelegt sein, dass Nicht-Administratoren Apps registrieren können. Sie müssen auch über eine Besitzer- oder Benutzerzugriffsadministratorrolle verfügen, um dem Dienstprinzipal eine Rolle zuzuweisen.  
>Weitere Informationen finden Sie unter [Erstellen einer Azure AD-App & Dienstprinzipals im Portal – Microsoft Identity Platform \| Microsoft-Dokumentation.](/azure/active-directory/develop/howto-create-service-principal-portal)

1. Erstellen Sie eine neue Registrierung (die inhärent einen Dienstprinzipal erstellt) in **Azure Active Directory \> App-Registrierungen \> Neue Registrierung.**

1. Füllen Sie das Formular nur mit dem Namen aus (es ist kein Umleitungs-URI erforderlich).

    ![Abbildung der Registrierung einer Anwendung](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![Abbildung der Übersichtsinformationen](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. Erstellen Sie einen geheimen Schlüssel, indem Sie auf **Zertifikate & geheimen \> Schlüsseln neuer geheimer Clientschlüssel** klicken:

    ![Abbildung von Zertifikaten und geheimen Schlüsseln](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
>**Sie können nicht erneut auf den geheimen Clientschlüssel zugreifen. Stellen Sie daher sicher, dass Sie ihn speichern.**

## <a name="setup-event-hub-namespace"></a>Setup Event Hub-Namespace


1. Erstellen sie einen Event Hub-Namespace:

    Wechseln **Sie zu "Event Hubs \> Hinzufügen",** und wählen Sie die Preisstufe, durchsatzeinheiten und die automatische Aufblasung (erfordert Standardpreise und unter Features) für die erwartete Last aus.  
    Weitere Informationen finden Sie unter [Preise – Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)

    >[!NOTE]
    > Sie können einen vorhandenen Event Hub verwenden, aber der Durchsatz und die Skalierung werden auf Namespaceebene festgelegt, daher wird empfohlen, einen Event Hub im zugehörigen Namespace zu platzieren.

   ![Abbildung des Event Hub-Namensraums](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. Sie benötigen auch die Ressourcen-ID dieses Event Hub-Namespace. Wechseln Sie zu den Eigenschaften ihrer Azure Event Hubs-Namespaceseite. \> Kopieren Sie den Text unter "Ressourcen-ID", und notieren Sie ihn für die Verwendung im abschnitt "M365-Konfiguration" weiter unten. 

    ![Abbildung der Eigenschaften](../../media/759498162a4e93cbf17c4130d704d164.png)

1. Nachdem der Event Hub-Namespace erstellt wurde, müssen Sie den App-Registrierungsdienstprinzipal als Leser, Azure Event Hubs-Datenempfänger und den Benutzer hinzufügen, der sich bei Microsoft 365 Defender als Mitwirkender anmeldet (dies kann auch auf Ressourcengruppen- oder Abonnementebene erfolgen).

    Dies geschieht in **Event Hubs Namespace \> Access Control (IAM) \> Hinzufügen** und Überprüfen unter **Rollenzuweisungen:**

    ![Abbildung der Zugriffssteuerung](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a>Setup Event Hub


**Option 1:**

Sie können einen Event Hub in Ihrem Namespace erstellen, und **alle** Ereignistypen (Tabellen), die Sie exportieren möchten, werden in **diesen** Event Hub geschrieben.

**Option 2:**

Anstatt alle Ereignistypen (Tabellen) in einen Event Hub zu exportieren, können Sie jede Tabelle in einen anderen Event Hub innerhalb des Event Hub-Namespace exportieren (einen Event Hub pro Ereignistyp).  

In dieser Option erstellt Microsoft 365 Defender Event Hubs für Sie.  
>[!NOTE]
> Wenn Sie einen Event Hub-Namespace verwenden, der **nicht** Teil eines Event Hub-Clusters ist, können Sie aufgrund einer Azure-Einschränkung von 10 Event Hubs pro Event Hub-Namespace nur bis zu 10 Ereignistypen (Tabellen) auswählen, die in jedem export Einstellungen exportiert werden sollen, den Sie definieren.

Beispiel:

![Abbildung des Beispiel-Event Hub](../../media/005c1f6c10c34420d387f594987f9ffe.png)

Wenn Sie diese Option auswählen, können Sie zum Abschnitt "Konfigurieren Microsoft 365 Defender zum Senden von [E-Mail-Tabellen"](#configure-microsoft-365-defender-to-send-email-tables) wechseln.

Erstellen Sie einen Event Hub in Ihrem Namespace, indem Sie **Event Hubs \> + Event Hub** auswählen.

Die Partitionsanzahl ermöglicht zusätzlichen Durchsatz über Parallelität. Daher wird empfohlen, diese Anzahl basierend auf der erwarteten Last zu erhöhen.  
Es werden standardmäßige Nachrichtenaufbewahrungs- und Aufnahmewerte von 1 und "Aus" empfohlen.

![Abbildung zum Erstellen des Event Hubs](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

Für diesen Event Hub (nicht namespace) müssen Sie eine Shared Access Policy mit Send, Listen Claims konfigurieren. Klicken Sie auf Ihre Richtlinien für den freigegebenen Zugriff auf **den Event Hub + \> \> Hinzufügen,** und geben Sie ihr dann einen Richtliniennamen (nicht an anderer Stelle verwendet), und aktivieren Sie **"Senden** und **Überwachen".**

![Abbildung der Richtlinien für den freigegebenen Zugriff](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>Konfigurieren Microsoft 365 Defender zum Senden von E-Mail-Tabellen


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a>Einrichten Microsoft 365 Defender Senden von E-Mail-Tabellen an Splunk über den Event Hub


1. Melden Sie sich bei Microsoft 365 Defender <https://security.microsoft.com> mit einem Konto an, das alle folgenden Rollenanforderungen erfüllt:

    - Rolle "Mitwirkender" auf der Event *Hub-Namespaceressourcenebene* oder höher für den Event Hub, in den Sie exportieren möchten. Ohne dies erhalten Sie einen Exportfehler, wenn Sie versuchen, die Einstellungen zu speichern.

    - Rolle "Globaler Administrator" oder "Sicherheitsadministrator" auf dem Mandanten, der an Microsoft 365 Defender und Azure gebunden ist.

    ![Abbildung des Sicherheitsportals](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. Klicken Sie auf **"Rohdatenexport" \> und "Hinzufügen".**

    Sie verwenden jetzt die Daten, die Sie oben notiert haben.

    **Name:** Dies ist lokal und sollte das sein, was in Ihrer Umgebung funktioniert.

    **Weiterleiten von Ereignissen an den Event Hub:** Aktivieren Sie dieses Kontrollkästchen.

    **Event-Hub-Ressourcen-ID:** Dies ist die Event Hub-Namespace-Ressourcen-ID, die Sie oben beim Einrichten des Event Hubs notiert haben.

    **Event-Hub-Name:** Wenn Sie einen Event Hub in Ihrem Event Hub-Namespace erstellt haben, fügen Sie den event Hub-Namen ein, den Sie oben notiert haben.

    Wenn Sie Microsoft 365 Defender das Erstellen von Event Hubs pro Ereignistypen (Tabellen) für Sie überlassen möchten, lassen Sie dieses Feld leer.

    **Ereignistypen:** Wählen Sie die Tabellen für die erweiterte Suche aus, die Sie an den Event Hub und dann an Ihre benutzerdefinierte App weiterleiten möchten. Warnungstabellen stammen aus Microsoft 365 Defender, Gerätetabellen stammen aus Microsoft Defender für Endpunkt (EDR), und E-Mail-Tabellen stammen aus Microsoft Defender für Office 365. E-Mail-Ereignisse zeichnet alle E-Mail-Transaktionen auf. Die URL (SafeLinks), Attachment (Safe Attachments) und Post Delivery Events (ZAP) werden ebenfalls aufgezeichnet und können mit den E-Mail-Ereignissen im NetworkMessageId-Feld verknüpft werden.

    ![Abbildung der Streaming-API-Einstellungen](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. Stellen Sie sicher, dass Sie auf **"Übermitteln"** klicken.

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a>Überprüfen, ob die Ereignisse in den Event Hub exportiert werden


Sie können überprüfen, ob Ereignisse an den Event Hub gesendet werden, indem Sie eine einfache Advanced Hunting-Abfrage ausführen. Wählen Sie **"Erweiterte \> Suche \> suchen" aus,** und geben Sie die folgende Abfrage ein:

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

Dies zeigt Ihnen, wie viele E-Mails in der letzten Stunde in allen anderen Tabellen eingegangen sind. Außerdem wird angezeigt, ob Ereignisse angezeigt werden, die in den Event Hub exportiert werden können. Wenn diese Anzahl 0 anzeigt, werden keine Daten angezeigt, die an den Event Hub gesendet werden.

![Abbildung der erweiterten Suche](../../media/c305e57dc6f72fa9eb035943f244738e.png)

Nachdem Sie überprüft haben, dass Daten exportiert werden müssen, können Sie den Event Hub anzeigen, um zu überprüfen, ob Nachrichten eintreffen. Dies kann bis zu einer Stunde dauern. 
 
1. Wechseln Sie in Azure zu **Event Hubs \> Click on the Namespace Event \> Hubs Click on the Event \> Hub**.  
1. Scrollen Sie unter **"Übersicht"** nach unten, und im Diagramm "Nachrichten" sollten eingehende Nachrichten angezeigt werden. Wenn keine Ergebnisse angezeigt werden, gibt es keine Nachrichten, die Ihre benutzerdefinierte App erfassen kann.

    ![Abbildung der Registerkarte "Übersicht" mit Nachrichten](../../media/e88060e315d76e74269a3fc866df047f.png)
