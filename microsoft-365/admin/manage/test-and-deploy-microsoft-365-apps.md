---
title: Testen und Bereitstellen von Microsoft 365-Apps durch Partner im Portal für integrierte Apps
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Suchen, Testen und Bereitstellen von Microsoft- und Microsoft-Partner-Apps für Benutzer und Gruppen in Ihrer Organisation über das Portal für integrierte Apps im Microsoft 365 Admin Center.
ms.openlocfilehash: f806d48e0ed582b1b5c1ee262058ce987125bd99
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488289"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>Testen und Bereitstellen von Microsoft 365-Apps durch Partner im Portal für integrierte Apps

Das Microsoft 365 Admin Center bietet Ihnen die Flexibilität, Apps mit einem einzigen Store, benutzerdefinierten Geschäftsanwendungen und Microsoft 365-Partner-Apps von einem einzigen Standort aus bereitstellen zu können. Der Zugriff auf den Speicherort finden Sie unter Microsoft Admin Center > Einstellungen > integrierten Apps. Die Möglichkeit, erworbene und lizenzierte Apps von Microsoft-Partnern über das Portal für integrierte Apps zu finden, zu testen und vollständig zu bereitstellen, bietet den Komfort und die Vorteile, die Ihre Organisation benötigt, um Geschäftsdienste regelmäßig auf dem neuesten Stand zu halten und effizient zu arbeiten.

Weitere Informationen zum Kauf und Zur Lizenzierung von Microsoft 365-Apps von Partnern für Ihre Organisation finden Sie unter [Manage and deploy Microsoft 365 Apps from the Microsoft 365 Admin Center](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).

Weitere Informationen zum Erstellen dieser Apps durch Partner finden Sie unter Planen eines [SaaS-Angebots für den kommerziellen Marketplace.](https://go.microsoft.com/fwlink/?linkid=2158277)

Das Portal für integrierte Apps ist nur für globale Administratoren zugänglich und nur für WorldWide-Kunden verfügbar. Dieses Feature ist in Denk- und Regierungswölkchen nicht verfügbar.

Das Portal für integrierte Apps zeigt eine Liste der Apps an, die einzelne Apps und Microsoft 365-Apps von Partnern enthält, die In Ihrer Organisation bereitgestellt werden. Nur Web-Apps, SPFx-Apps, Office-Add-Ins und Teams-Apps werden aufgelistet. Für Web-Apps werden 2 Arten von Apps angezeigt.

- SaaS-Apps, die in appsource.microsoft.com verfügbar sind und von Administratoren bereitgestellt werden können, die im Namen der Organisation zustimmen.
- SAML-Katalog-Apps, die mit Office-Add-Ins verknüpft sind.

## <a name="manage-apps-in-the-integrated-apps-portal"></a>Verwalten von Apps im Portal für integrierte Apps

Sie können das Testen und Die Bereitstellung von gekauften und lizenzierten Microsoft 365-Apps von Partnern verwalten.

1. Wählen Sie im Admin Center im linken Navigations navi die Option **Einstellungen** aus, und wählen Sie dann **Integrierte Apps aus.**

2. Wählen Sie eine App **mit status** of More apps **available aus,** um den Bereich **Verwalten zu** öffnen. Der Status von **weiteren verfügbaren Apps** zeigt, dass es mehr Integrationen von ISVs gibt, die noch nicht bereitgestellt wurden.

3. Wählen Sie **auf der Registerkarte** Übersicht die Option Bereitstellen **aus.** Für einige Apps müssen Sie Benutzer hinzufügen, bevor Sie Bereitstellen auswählen können.

4. Wählen **Sie Benutzer** aus, wählen Sie Ist **dies eine Testbereitstellung,** und wählen Sie dann Gesamte **Organisation,** **bestimmte Benutzer/Gruppen** oder **Just me aus.** Sie können auch test **deployment auswählen,** wenn Sie die Bereitstellung der App für die gesamte Organisation abwarten möchten. Bestimmte Benutzer oder Gruppen können eine Microsoft 365-Gruppe, eine Sicherheitsgruppe oder eine Verteilergruppe sein.

5. Wählen **Sie Aktualisieren** und dann Fertig **aus.** Sie können jetzt auf der Registerkarte Übersicht die Option Bereitstellen auswählen.

6. Überprüfen Sie die App-Informationen, und wählen Sie dann **Bereitstellen aus.**

7. Wählen **Sie auf** der Seite Bereitstellung abgeschlossen die Option Fertig aus, und überprüfen Sie die Details des Tests oder der vollständigen Bereitstellung auf der Registerkarte Übersicht. 

8. Wenn die App den Status **Ausstehendes Update** hat, können Sie auf die App klicken, um den Bereich Verwalten zu öffnen und die App zu aktualisieren.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Suchen veröffentlichter Apps für Tests und vollständige Bereitstellung

Sie können veröffentlichte Apps finden, testen und vollständig bereitstellen, die noch nicht in der Liste auf der Seite Integrierte Apps angezeigt werden. Durch den Kauf und die Lizenzierung der Apps im Admin Center können Sie Microsoft- und Microsoft-Partner-Apps an einem einzigen Speicherort zu Ihrer Liste hinzufügen.

1. Wählen Sie im Admin Center im linken Navigations navi die Option **Einstellungen** aus, und wählen Sie dann **Integrierte Apps aus.**

2. Wählen **Sie Apps herunterladen** aus, um eine Ansicht der Apps zu erhalten.

3. Wählen Sie auf der **Seite veröffentlichte Microsoft 365 Apps-Apps** die App aus, die Sie bereitstellen möchten, indem Sie Jetzt herunterladen **auswählen.** Die angezeigten Apps sind in erster Linie Word, PowerPoint, Excel, Outlook-Add-Ins, Teams-App und SharePoint-Apps (auf SharePoint Framework-Technologie aufgebaut). Akzeptieren Sie die Berechtigungen, und wählen Sie **Weiter aus.**

5. Wählen **Sie oben** auf der Seite neben der Nachricht bereitstellen aus, die auf das Warten auf die Bereitstellung verweist.

    Wenn die ausgewählte App von einem ISV mit einem SaaS-Angebot verknüpft ist, werden alle anderen Apps, die Teil dieses verknüpften Angebots sind, auf der Seite Konfiguration angezeigt. Wenn Sie alle Apps bereitstellen möchten, wählen Sie **Weiter aus.** Wählen Sie andernfalls **Bearbeiten** aus, und wählen Sie aus, welche Apps bereitgestellt werden soll. Für einige Apps müssen Sie Benutzer hinzufügen, bevor Sie **Bereitstellen auswählen können.**

6. Wählen **Sie Benutzer hinzufügen** aus, wählen Sie Ist **dies eine Testbereitstellung,** und wählen Sie dann **Gesamte** Organisation oder **Bestimmte Benutzer/Gruppen** oder **Just me aus.**

    Bestimmte Benutzer/Gruppen können eine Microsoft 365-Gruppe, eine Sicherheitsgruppe oder eine verteilte Gruppe sein. Sie können auch test **deployment auswählen,** wenn Sie die Bereitstellung der App für die gesamte Organisation abwarten möchten.

7. Wählen **Sie Weiter** aus, um zur Seite Berechtigungsanforderung akzeptieren **zu** gelangen. Die Funktionen und Berechtigungen der einzelnen Apps werden aufgelistet. Wenn die App ihre Zustimmung benötigt, wählen Sie **Berechtigungen akzeptieren aus.** Nur ein globaler Administrator kann zustimmen.

8. Wählen **Sie Weiter** aus, um die Bereitstellung zu überprüfen, und wählen Sie Bereitstellung fertig stellen **aus.** Sie können die Bereitstellung auf der Registerkarte **Übersicht** anzeigen, indem Sie **Diese Bereitstellung anzeigen auswählen.** Im Microsoft 365 Admin Center sehen Sie den Status der einzelnen bereitgestellten Apps und das Datum, an dem Sie die App bereitgestellt haben.

> [!NOTE]
> Wenn eine App zuvor von einem anderen Ort als dem Portal für integrierte Apps bereitgestellt wurde, ist der **Bereitstellungstyp** **Benutzerdefinierter.**

## <a name="unsupported-scenarios"></a>Nicht unterstützte Szenarien

Für die folgenden Szenarien können Sie keine einzelne Store-App oder Microsoft 365-Apps von Einem Partner über das Portal für integrierte Apps bereitstellen.

- Das gleiche Add-In ist mit mehreren SaaS-Angeboten verknüpft.
- Das SaaS-Angebot ist mit Add-Ins verknüpft, kann jedoch nicht in Microsoft Graph integriert werden, und es wird keine AAD-App-ID bereitgestellt.
- Das SaaS-Angebot ist mit Add-Ins verknüpft, aber die für die Microsoft Graph-Integration bereitgestellte AAD-App-ID wird für mehrere SaaS-Angebote freigegeben.

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Hochladen benutzerdefinierter Business-Apps für Tests und vollständige Bereitstellung

1. Wählen Sie im Admin Center im linken Navigations navi die Option **Einstellungen** und dann **Integrierte Apps aus.**

2. Wählen **Sie Benutzerdefinierte Apps hochladen aus.** Es wird nur eine benutzerdefinierte Reihe von Apps für Word, PowerPoint, Excel und Outlook unterstützt.

3. Laden Sie die Manifestdatei von Ihrem Gerät hoch, oder fügen Sie einen URL-Link hinzu. Für einige Apps müssen Sie Benutzer hinzufügen, bevor Sie Bereitstellen auswählen können.

4. Wählen **Sie Benutzer hinzufügen** aus, wählen Sie Ist **dies eine Testbereitstellung,** und wählen Sie **Gesamte Organisation** oder Bestimmte **Benutzer/Gruppen** oder **Just me aus.**

    Bestimmte Benutzer/Gruppen können eine Microsoft 365-Gruppe, eine Sicherheitsgruppe oder eine verteilte Gruppe sein. Sie können auch test **deployment auswählen,** wenn Sie warten möchten, bis die App in der gesamten Organisation bereitgestellt wird.

5. Wählen **Sie Weiter** aus, um zur Seite Berechtigungsanforderung akzeptieren **zu** gelangen. Die Funktionen und Berechtigungen der Apps werden aufgelistet. Wenn die App ihre Zustimmung benötigt, wählen Sie **Berechtigungen akzeptieren aus.** Nur ein globaler Administrator kann zustimmen.

6. Wählen **Sie Weiter** aus, um die Bereitstellung zu überprüfen, und wählen Sie Bereitstellung fertig stellen **aus.** Sie können die Bereitstellung auf der Registerkarte **Übersicht** anzeigen, indem Sie **Diese Bereitstellung anzeigen auswählen.**

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>Welche Administratorrolle muss ich für den Zugriff auf integrierte Apps verwenden?

Nur globale Administratoren können auf integrierte Apps zugreifen. Integrierte Apps werden nicht im linken Navigations navi für andere Administratoren angezeigt.

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>Warum wird das Add-In im linken Navigations navig unter Einstellung, aber nicht integrierte Apps angezeigt?

Es gibt einige Gründe:

- Der angemeldete Administrator ist ein Exchange-Administrator.
- Der Kunde befindet sich in einer unabhängigen Cloud, und integrierte Apps stehen für kundenorientierte Cloudkunden noch zur Verfügung.

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>Welche Apps kann ich über integrierte Apps bereitstellen?

Integrierte Apps ermöglichen die Bereitstellung von Web Apps, Teams-App, Excel, PowerPoint, Word, Outlook-Add-Ins und SPFx-Apps. Für Add-Ins unterstützen integrierte Apps die Bereitstellung in Exchange-Onlinepostfächern und nicht in lokalen Exchange-Postfächern.

### <a name="can-administrators-delete-or-remove-apps"></a>Können Administratoren Apps löschen oder entfernen?

Ja. Globale Administratoren können Apps löschen oder entfernen.

- Wählen Sie eine App aus der Listenansicht aus. Wählen Sie **auf der** Registerkarte Konfiguration aus, welche Apps entfernt werden.  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>Sind integrierte Apps in der cloudbasierten Cloud verfügbar?

Nein. Integrierte Apps sind für kundenbasierte Cloudkunden nicht verfügbar.

### <a name="is-integrated-apps-available-in-government-clouds"></a>Sind integrierte Apps in Government Clouds verfügbar?

Nein. Integrierte Apps sind für Government Cloud-Kunden nicht verfügbar.
