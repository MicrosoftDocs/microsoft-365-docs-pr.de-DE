---
title: Erstellen und Verwalten von Gerätegruppen in Microsoft Defender für Endpunkt
description: Erstellen Sie Gerätegruppen, und legen Sie automatisierte Korrekturstufen für sie fest, indem Sie die für die Gruppe geltenden Regeln bestätigen.
keywords: Gerätegruppen, Gruppen, Korrektur, Ebene, Regeln, AAD-Gruppe, Rolle, zuweisen, Rangfolge
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
ms.openlocfilehash: 49bd90d8a082f55622e54976cc8fc78229d8c646
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453537"
---
# <a name="create-and-manage-device-groups"></a>Erstellen und Verwalten von Gerätegruppen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- Azure Active Directory
- Office 365

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


In einem Unternehmensszenario werden Sicherheitsteams in der Regel eine Gruppe von Geräten zugewiesen. Diese Geräte werden basierend auf einer Reihe von Attributen wie Domänen, Computernamen oder bestimmten Tags gruppiert.

In Microsoft Defender für Endpunkt können Sie Gerätegruppen erstellen und für Folgendes verwenden:
- Beschränken des Zugriffs auf verwandte Warnungen und Daten auf bestimmte Azure AD-Benutzergruppen mit [zugewiesenen RBAC-Rollen](rbac.md) 
- Konfigurieren unterschiedlicher Einstellungen für die automatische Problembehebung für unterschiedliche Gerätegruppen
- Zuweisen bestimmter Korrekturstufen, die während automatisierter Untersuchungen angewendet werden sollen
- Filtern Sie in einer Untersuchung die **Geräteliste** mithilfe des **Gruppenfilters** nach bestimmten Gerätegruppen.

Sie können Gerätegruppen im Kontext des rollenbasierten Zugriffs (Role-Based Access, RBAC) erstellen, um zu steuern, wer bestimmte Aktionen ausführen oder Informationen anzeigen kann, indem Sie einer Benutzergruppe die Gerätegruppen zuweisen. Weitere Informationen finden Sie unter [Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung.](rbac.md)

>[!TIP]
> Einen umfassenden Einblick in die RBAC-Anwendung finden Sie unter: [Wird Ihr SOC flach mit RBAC ausgeführt.](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)

Im Rahmen des Erstellungsprozesses einer Gerätegruppe gehen Sie folgendermaßen vor:
- Legen Sie die automatische Korrekturstufe für diese Gruppe fest. Weitere Informationen zu Korrekturstufen finden Sie unter [Verwenden der automatisierten Untersuchung, um Bedrohungen zu untersuchen und zu beheben.](automated-investigations.md)
- Geben Sie die Übereinstimmungsregel an, die basierend auf dem Gerätenamen, der Domäne, den Tags und der Betriebssystemplattform bestimmt, welche Gerätegruppe zur Gruppe gehört. Wenn ein Gerät auch anderen Gruppen zugeordnet ist, wird es nur der Gerätegruppe mit dem höchsten Rang hinzugefügt.
- Wählen Sie die Azure AD-Benutzergruppe aus, die Zugriff auf die Gerätegruppe haben soll.
- Rangfolge der Gerätegruppe relativ zu anderen Gruppen nach der Erstellung.

>[!NOTE]
>Eine Gerätegruppe ist für alle Benutzer zugänglich, wenn Sie ihr keine Azure AD-Gruppen zuweisen.

## <a name="create-a-device-group"></a>Erstellen einer Gerätegruppe

1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Endpunktberechtigungsgerätegruppen**  >    >  aus.

2. Klicken Sie auf **"Gerätegruppe hinzufügen".**

3. Geben Sie den Gruppennamen und die Automatisierungseinstellungen ein, und geben Sie die entsprechende Regel an, die bestimmt, welche Geräte zur Gruppe gehören. Erfahren [Sie, wie die automatisierte Untersuchung beginnt.](automated-investigations.md#how-the-automated-investigation-starts)

    >[!TIP]
    >Wenn Sie Geräte nach Organisationseinheit gruppieren möchten, können Sie den Registrierungsschlüssel für die Gruppenmitgliedschaft konfigurieren. Weitere Informationen zum Gerätetagging finden Sie unter [Erstellen und Verwalten von Gerätetags.](machine-tags.md)

4. Anzeigen einer Vorschau mehrerer Geräte, die mit dieser Regel übereinstimmen. Wenn Sie mit der Regel zufrieden sind, klicken Sie auf die Registerkarte **"Benutzerzugriff".**

5. Weisen Sie die Benutzergruppen zu, die auf die von Ihnen erstellte Gerätegruppe zugreifen können.

    >[!NOTE]
    >Sie können nur Azure AD-Benutzergruppen Zugriff gewähren, die RBAC-Rollen zugewiesen wurden.

6. Klicken Sie auf **Schließen**. Die Konfigurationsänderungen werden angewendet.

## <a name="manage-device-groups"></a>Verwalten von Gerätegruppen

Sie können den Rang einer Gerätegruppe höher oder tiefer stufen, sodass sie während des Abgleichs eine höhere oder niedrigere Priorität erhält. Wenn ein Gerät mit mehr als einer Gruppe abgeglichen wird, wird es nur der Gruppe mit dem höchsten Rang hinzugefügt. Sie können auch Gruppen bearbeiten und löschen.



>[!WARNING]
>Das Löschen einer Gerätegruppe kann sich auf E-Mail-Benachrichtigungsregeln auswirken. Wenn eine Gerätegruppe unter einer E-Mail-Benachrichtigungsregel konfiguriert ist, wird sie aus dieser Regel entfernt. Wenn die Gerätegruppe die einzige Gruppe ist, die für eine E-Mail-Benachrichtigung konfiguriert ist, wird diese E-Mail-Benachrichtigungsregel zusammen mit der Gerätegruppe gelöscht.

Standardmäßig sind Gerätegruppen für alle Benutzer mit Portalzugriff zugänglich. Sie können das Standardverhalten ändern, indem Sie der Gerätegruppe Azure AD-Benutzergruppen zuweisen.

Geräte, die keiner Gruppe zugeordnet sind, werden der Gruppe "Nicht gruppierte Geräte" (Standardgruppe) hinzugefügt. Sie können den Rang dieser Gruppe nicht ändern oder löschen. Sie können jedoch die Korrekturstufe dieser Gruppe ändern und die Azure AD-Benutzergruppen definieren, die auf diese Gruppe zugreifen können.

>[!NOTE]
> Das Anwenden von Änderungen an der Gerätegruppenkonfiguration kann bis zu mehrere Minuten dauern.


### <a name="add-device-group-definitions"></a>Hinzufügen von Gerätegruppendefinitionen
Gerätegruppendefinitionen können auch mehrere Werte für jede Bedingung enthalten. Sie können mehrere Tags, Gerätenamen und Domänen auf die Definition einer einzelnen Gerätegruppe festlegen.

1. Erstellen Sie eine neue Gerätegruppe, und wählen Sie dann die Registerkarte **"Geräte"** aus.
2. Fügen Sie den ersten Wert für eine der Bedingungen hinzu.
3. Wählen Sie `+` diese Option aus, um weitere Zeilen desselben Eigenschaftstyps hinzuzufügen.

>[!TIP]
> Verwenden Sie den Operator "OR" zwischen Zeilen desselben Bedingungstyps, der mehrere Werte pro Eigenschaft zulässt.
> Sie können bis zu 10 Zeilen (Werte) für jeden Eigenschaftstyp hinzufügen – Tag, Gerätename, Domäne.

Weitere Informationen zum Verknüpfen mit Gerätegruppendefinitionen finden Sie unter ["Gerätegruppen – Microsoft 365 Sicherheit".](https://sip.security.microsoft.com/homepage)

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung](rbac.md)
- [Erstellen und Verwalten von Gerätekategorien](machine-tags.md)
- [Abrufen einer Liste von Mandantengerätegruppen mithilfe Graph API](/graph/api/device-list-memberof)
