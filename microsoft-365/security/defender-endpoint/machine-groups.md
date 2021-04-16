---
title: Erstellen und Verwalten von Gerätegruppen in Microsoft Defender for Endpoint
description: Erstellen von Gerätegruppen und Festlegen automatisierter Behebungsstufen für diese Gruppen, indem Sie die regeln, die für die Gruppe gelten, verwechseln
keywords: Gerätegruppen, Gruppen, Korrektur, Ebene, Regeln,Ad-Gruppe, Rolle, Zuweisen, Rang
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: acd24e5c87a74bbb32835ec170a121c5c0b6bb33
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860303"
---
# <a name="create-and-manage-device-groups"></a>Erstellen und Verwalten von Gerätegruppen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- Azure Active Directory
- Office 365

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


In einem Unternehmensszenario wird Sicherheitsbetriebsteams in der Regel eine Reihe von Geräten zugewiesen. Diese Geräte werden basierend auf einer Reihe von Attributen wie ihren Domänen, Computernamen oder festgelegten Tags gruppieren.

In Microsoft Defender for Endpoint können Sie Gerätegruppen erstellen und verwenden, um:
- Einschränken des Zugriffs auf verwandte Warnungen und Daten auf bestimmte Azure AD-Benutzergruppen mit [zugewiesenen ROLLEN-ROLLEN](rbac.md) 
- Konfigurieren verschiedener Einstellungen für die automatische Korrektur für verschiedene Gerätegruppen
- Zuweisen bestimmter Korrekturstufen, die während automatisierter Untersuchungen angewendet werden
- Filtern Sie in einer Untersuchung die **Liste Geräte** mithilfe des Gruppenfilters nach **bestimmten Gerätegruppen.**

Sie können Gerätegruppen im Kontext des rollenbasierten Zugriffs (Role-Based Access, RBAC) erstellen, um zu steuern, wer bestimmte Aktionen ergreifen kann, oder Informationen sehen, indem Sie die Gerätegruppen einer Benutzergruppe zuweisen. Weitere Informationen finden Sie unter [Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung](rbac.md).

>[!TIP]
> Einen umfassenden Einblick in die RBAC-Anwendung finden Sie unter: [Wird Ihr SOC mit RBAC flach ausgeführt.](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)

Im Rahmen des Erstellens einer Gerätegruppe werden Sie:
- Legen Sie die automatische Behebungsstufe für diese Gruppe fest. Weitere Informationen zu Korrekturstufen finden Sie unter Verwenden der automatisierten Untersuchung zum Untersuchen und Behebung [von Bedrohungen](automated-investigations.md).
- Geben Sie die Übereinstimmende Regel an, die bestimmt, welche Gerätegruppe zu der Gruppe gehört, basierend auf dem Gerätenamen, der Domäne, den Tags und der Betriebssystemplattform. Wenn ein Gerät auch mit anderen Gruppen abgestimmt ist, wird es nur der am höchsten bewerteten Gerätegruppe hinzugefügt.
- Wählen Sie die Azure AD-Benutzergruppe aus, die Zugriff auf die Gerätegruppe haben soll.
- Rangieren Sie die Gerätegruppe relativ zu anderen Gruppen, nachdem sie erstellt wurde.

>[!NOTE]
>Auf eine Gerätegruppe kann für alle Benutzer zugegriffen werden, wenn Sie ihr keine Azure AD-Gruppen zuweisen.

## <a name="create-a-device-group"></a>Erstellen einer Gerätegruppe

1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Gerätegruppen aus.**

2. Klicken **Sie auf Gerätegruppe hinzufügen.**

3. Geben Sie den Gruppennamen und die Automatisierungseinstellungen ein, und geben Sie die Übereinstimmungsregel an, die bestimmt, welche Geräte zur Gruppe gehören. Weitere [Informationen finden Sie unter Starten der automatisierten Untersuchung.](automated-investigations.md#how-the-automated-investigation-starts)

    >[!TIP]
    >Wenn Sie Geräte nach Organisationseinheit gruppieren möchten, können Sie den Registrierungsschlüssel für die Gruppenzugehörigkeit konfigurieren. Weitere Informationen zum Taggen von Geräten finden Sie unter [Create and manage device tags](machine-tags.md).

4. Zeigen Sie eine Vorschau mehrerer Geräte an, die mit dieser Regel übereinstimmen. Wenn Sie mit der Regel zufrieden sind, klicken Sie auf die **Registerkarte Benutzerzugriff.**

5. Weisen Sie die Benutzergruppen zu, die auf die von Ihnen erstellte Gerätegruppe zugreifen können.

    >[!NOTE]
    >Sie können nur Zugriff auf Azure AD-Benutzergruppen gewähren, die ROLLENAC-Rollen zugewiesen wurden.

6. Klicken Sie auf **Schließen**. Die Konfigurationsänderungen werden angewendet.

## <a name="manage-device-groups"></a>Verwalten von Gerätegruppen

Sie können die Rangfolge einer Gerätegruppe höher oder tieferstufen, sodass sie beim Abgleich eine höhere oder niedrigere Priorität hat. Wenn ein Gerät mit mehreren Gruppen abgestimmt ist, wird es nur der gruppe mit der höchsten Rangranggruppe hinzugefügt. Sie können auch Gruppen bearbeiten und löschen.

>[!WARNING]
>Das Löschen einer Gerätegruppe kann sich auf E-Mail-Benachrichtigungsregeln auswirken. Wenn eine Gerätegruppe unter einer E-Mail-Benachrichtigungsregel konfiguriert ist, wird sie aus dieser Regel entfernt. Wenn die Gerätegruppe die einzige Gruppe ist, die für eine E-Mail-Benachrichtigung konfiguriert ist, wird diese E-Mail-Benachrichtigungsregel zusammen mit der Gerätegruppe gelöscht.

Standardmäßig sind Gerätegruppen für alle Benutzer mit Portalzugriff zugänglich. Sie können das Standardverhalten ändern, indem Sie der Gerätegruppe Azure AD-Benutzergruppen zuweisen.

Geräte, die nicht mit Gruppen übereinstimmen, werden der Gruppe Nicht gruppierende Geräte (Standard)-Gruppe hinzugefügt. Sie können den Rang dieser Gruppe nicht ändern oder löschen. Sie können jedoch die Behebungsstufe dieser Gruppe ändern und die Azure AD-Benutzergruppen definieren, die auf diese Gruppe zugreifen können.

>[!NOTE]
> Das Anwenden von Änderungen an der Gerätegruppenkonfiguration kann bis zu mehrere Minuten dauern.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung](rbac.md)
- [Erstellen und Verwalten von Gerätekategorien](machine-tags.md)
- [Abrufen einer Liste der Mandantengerätegruppen mithilfe der Graph-API](https://docs.microsoft.com/graph/api/device-list-memberof)
