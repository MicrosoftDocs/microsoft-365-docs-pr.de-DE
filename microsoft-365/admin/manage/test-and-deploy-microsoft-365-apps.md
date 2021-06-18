---
title: Testen und Bereitstellen von Microsoft 365 Apps von Partnern im Portal für integrierte Apps
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
ms.openlocfilehash: dcd4a91d9e43c0a740094615cd3dca0b0e8bc0f6
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007057"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>Testen und Bereitstellen von Microsoft 365 Apps von Partnern im Portal für integrierte Apps

Die Microsoft 365 Admin Center bietet Ihnen die Flexibilität, Einzelspeicher-Apps, benutzerdefinierte Branchen-Apps und Microsoft 365 Partner-Apps von einem einzigen Standort aus bereitzustellen. Auf den Speicherort kann in den Einstellungen des Microsoft Admin Centers in integrierten Apps zugegriffen werden. Die Möglichkeit, gekaufte und lizenzierte Apps von Microsoft-Partnern über das Portal für integrierte Apps zu finden, zu testen und vollständig bereitzustellen, bietet den Komfort und die Vorteile, die Ihre Organisation benötigt, um Geschäftsdienste regelmäßig auf dem neuesten Stand zu halten und effizient zu arbeiten.

Weitere Informationen zum Kauf und zur Lizenzierung Microsoft 365 Apps von Partnern für Ihre Organisation finden Sie unter [Verwalten und Bereitstellen von Microsoft 365 Apps aus der Microsoft 365 Admin Center.](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)

Weitere Informationen dazu, wie Partner diese Apps erstellen, finden Sie unter ["Planen eines SaaS-Angebots für den kommerziellen Marketplace"](https://go.microsoft.com/fwlink/?linkid=2158277)

Das Portal für integrierte Apps ist nur für globale Administratoren zugänglich und nur für weltweite Kunden verfügbar. Dieses Feature ist in unabhängigen Und Government-Clouds nicht verfügbar.

Das Portal für integrierte Apps zeigt eine Liste von Apps an, die einzelne Apps und Microsoft 365 Apps von Partnern enthält, die In Ihrer Organisation bereitgestellt werden. Es werden nur Web-Apps, SPFx-Apps, Office-Add-Ins und Teams Apps aufgeführt. Für Web-Apps können Sie zwei Arten von Apps anzeigen.

- SaaS-Apps, die in appsource.microsoft.com verfügbar sind und von Administratoren bereitgestellt werden können, die ihre Zustimmung im Namen der Organisation geben.
- SAML-Katalog-Apps, die mit Office-Add-Ins verknüpft sind.

## <a name="manage-apps-in-the-integrated-apps-portal"></a>Verwalten von Apps im Portal für integrierte Apps

Sie können tests und die Bereitstellung von erworbenen und lizenzierten Microsoft 365 Apps von Partnern verwalten.

1. Wählen Sie im Admin Center **Einstellungen** und dann **integrierte Apps** aus.

2. Wählen Sie eine App mit **dem Status** **"Weitere Apps" aus,** um den Bereich **"Verwalten"** zu öffnen. Der Status **weiterer verfügbarer Apps** teilt Ihnen mit, dass es mehr Integrationen von den ISVs gibt, die noch nicht bereitgestellt wurden.

3. Wählen Sie auf der Registerkarte **"Übersicht"** die Option **"Bereitstellen" aus.** Einige Apps erfordern, dass Sie Benutzer hinzufügen, bevor Sie "Bereitstellen" auswählen können.

4. Wählen Sie  **"Benutzer"** aus, wählen Sie **"Ist dies eine Testbereitstellung"** aus, und wählen Sie dann **"Gesamte Organisation",** **"Bestimmte Benutzer/Gruppen"** oder **"Nur ich"** aus. Sie können auch **"Testbereitstellung"** auswählen, wenn Sie warten möchten, bis die App für die gesamte Organisation bereitgestellt wird. Bestimmte Benutzer oder Gruppen können eine Microsoft 365 Gruppe, eine Sicherheitsgruppe oder eine Verteilergruppe sein.

5. Wählen Sie **"Aktualisieren"** und dann **"Fertig"** aus. Sie können jetzt auf der Registerkarte "Übersicht" die Option "Bereitstellen" auswählen.

6. Überprüfen Sie die App-Informationen, und wählen Sie dann **Bereitstellen aus.**

7. Wählen Sie auf der Seite "Bereitstellung abgeschlossen" die Option **"Fertig"** aus, und überprüfen Sie die Details des Tests oder der vollständigen Bereitstellung auf der Registerkarte **"Übersicht".**

8. Wenn die App den Status **"Update ausstehend"** aufweist, können Sie auf die App klicken, um den Bereich "Verwalten" zu öffnen und die App zu aktualisieren.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Suchen nach veröffentlichten Apps zum Testen und zur vollständigen Bereitstellung

Sie können veröffentlichte Apps, die noch nicht in der Liste auf der Seite "Integrierte Apps" angezeigt werden, suchen, testen und vollständig bereitstellen. Durch den Kauf und die Lizenzierung der Apps über das Admin Center können Sie Microsoft- und Microsoft-Partner-Apps von einem einzigen Ort aus zu Ihrer Liste hinzufügen.

1. Wählen Sie im Admin Center im linken Navigationsbereich **Einstellungen** und dann **integrierte Apps** aus.

2. Wählen Sie **"Apps abrufen"** aus, um eine Ansicht der Apps zu erhalten.

3. Wählen Sie auf der Seite **Microsoft 365 Apps** veröffentlichte Apps die App aus, die Sie bereitstellen möchten, indem Sie **"Jetzt abrufen"** auswählen. Die angezeigten Apps sind in erster Linie Word-, PowerPoint-, Excel-, Outlook-Add-Ins, Teams-App und SharePoint-Apps (basierend auf SharePoint-Framework Technologie). Akzeptieren Sie die Berechtigungen, und wählen Sie **"Weiter"** aus.

5. Wählen Sie oben auf der Seite neben der Nachricht, die sich auf das Warten auf die Bereitstellung bezieht, **"Bereitstellen"** aus.

    Wenn die ausgewählte App von einem ISV mit einem SaaS-Angebot verknüpft ist, werden alle anderen Apps, die Teil dieses verknüpften Angebots sind, auf der Konfigurationsseite angezeigt. Wenn Sie alle Apps bereitstellen möchten, wählen Sie **"Weiter"** aus. Wählen Sie andernfalls **"Bearbeiten"** aus, und wählen Sie aus, welche Apps bereitgestellt werden sollen. Einige Apps erfordern, dass Sie Benutzer hinzufügen, bevor Sie **"Bereitstellen"** auswählen können.

6. Wählen Sie **"Benutzer hinzufügen",** **"Ist dies eine Testbereitstellung"** und dann **"Gesamte Organisation"** oder **"Bestimmte Benutzer/Gruppen"** oder **"Nur ich"** aus.

    Bestimmte Benutzer/Gruppen können eine Microsoft 365 Gruppe, eine Sicherheitsgruppe oder eine verteilte Gruppe sein. Sie können auch **"Testbereitstellung"** auswählen, wenn Sie warten möchten, bis die App für die gesamte Organisation bereitgestellt wird.

7. Wählen Sie **"Weiter"** aus, um zur Seite **"Berechtigungsanforderung annehmen"** zu gelangen. Die App-Funktionen und -Berechtigungen der einzelnen Apps werden aufgelistet. Wenn die App die Zustimmung benötigt, wählen Sie **Berechtigungen akzeptieren** aus. Nur ein globaler Administrator kann seine Zustimmung erteilen.

8. Wählen Sie **"Weiter"** aus, um die Bereitstellung zu überprüfen, und wählen Sie **"Bereitstellung fertig stellen"** aus. Sie können die Bereitstellung auf der Registerkarte **"Übersicht"** anzeigen, indem Sie **"Diese Bereitstellung anzeigen"** auswählen. Im Microsoft 365 Admin Center können Sie den Status jeder bereitgestellten App und das Datum der Bereitstellung der App anzeigen.

> [!NOTE]
> Wenn eine App zuvor von einer anderen Stelle als dem Portal für integrierte Apps bereitgestellt wurde, ist der **Bereitstellungstyp** **"Benutzerdefiniert".**

## <a name="unsupported-scenarios"></a>Nicht unterstützte Szenarien

Sie können keine einzelne Store-App oder Microsoft 365 Apps vom Partner über das Portal für integrierte Apps für die folgenden Szenarien bereitstellen.

- Das gleiche Add-In ist mit mehreren SaaS-Angeboten verknüpft.
- Das SaaS-Angebot ist mit Add-Ins verknüpft, kann jedoch nicht in Microsoft Graph integriert werden, und es wird keine AAD-App-ID bereitgestellt.
- Das SaaS-Angebot ist mit Add-Ins verknüpft, aber die für Microsoft bereitgestellte AAD-App-ID Graph Integration wird für mehrere SaaS-Angebote freigegeben.

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Hochladen benutzerdefinierte Branchen-Apps für Tests und vollständige Bereitstellung

1. Wählen Sie im Admin Center im linken Navigationsbereich **Einstellungen** und dann **integrierte Apps** aus.

2. Wählen Sie **Hochladen benutzerdefinierte Apps** aus. Es wird nur eine benutzerdefinierte App-Zeile für Word, PowerPoint, Excel und Outlook unterstützt.

3. Hochladen Sie die Manifestdatei von Ihrem Gerät aus, oder fügen Sie einen URL-Link hinzu. Einige Apps erfordern, dass Sie Benutzer hinzufügen, bevor Sie "Bereitstellen" auswählen können.

4. Wählen Sie **"Benutzer hinzufügen",** **"Ist dies eine Testbereitstellung"** und wählen Sie **"Gesamte Organisation"** oder **"Bestimmte Benutzer/Gruppen"** oder **"Nur ich"** aus.

    Bestimmte Benutzer/Gruppen können eine Microsoft 365 Gruppe, eine Sicherheitsgruppe oder eine verteilte Gruppe sein. Sie können auch **"Testbereitstellung"** auswählen, wenn Sie warten möchten, bis die App für die gesamte Organisation bereitgestellt wird.

5. Wählen Sie **"Weiter"** aus, um zur Seite **"Berechtigungsanforderung annehmen"** zu gelangen. Die App-Funktionen und -Berechtigungen der Apps sind aufgeführt. Wenn die App die Zustimmung benötigt, wählen Sie **Berechtigungen akzeptieren** aus. Nur ein globaler Administrator kann seine Zustimmung erteilen.

6. Wählen Sie **"Weiter"** aus, um die Bereitstellung zu überprüfen, und wählen Sie **"Bereitstellung fertig stellen"** aus. Sie können die Bereitstellung auf der Registerkarte **"Übersicht"** anzeigen, indem Sie **"Diese Bereitstellung anzeigen"** auswählen.

## <a name="prepare-to-deploy-add-ins-in-integrated-apps"></a>Vorbereiten der Bereitstellung von Add-Ins in integrierten Apps

Office-Add-Ins helfen Ihnen, Ihre Dokumente zu personalisieren und den Zugriff auf Informationen im Web zu optimieren (siehe Start using your Office Add-in). 

Add-Ins bieten die folgenden Vorteile: 

- Wenn die relevante Office Anwendung gestartet wird, wird das Add-In automatisch heruntergeladen. Wenn das Add-In Add-In-Befehle unterstützt, wird das Add-In automatisch im Menüband innerhalb der Office-Anwendung angezeigt. 

- Add-Ins werden für Benutzer nicht mehr angezeigt, wenn der Administrator das Add-In deaktiviert oder löscht oder wenn der Benutzer aus Azure Active Directory oder aus einer Gruppe entfernt wird, der das Add-In zugewiesen ist. 

Add-Ins werden auf drei Desktopplattformen Windows, Mac und Online Office-Apps unterstützt. Es wird auch in iOS und Android unterstützt (nur Outlook mobile Add-Ins). 

Es kann bis zu 24 Stunden dauern, bis ein Add-In für alle Benutzer für den Client angezeigt wird. 

Heute können sowohl Exchange-Administratoren als auch globale Administratoren Add-Ins aus integrierten Apps bereitstellen.   

### <a name="before-you-begin"></a>Bevor Sie beginnen

Für die Bereitstellung von Add-Ins müssen die Benutzer Microsoft 365 Enterprise Lizenzen (E3/E5/F3) oder Microsoft 365 Business-Lizenzen (Business Basic, Business Standard, Business Premium) verwenden. Die Benutzer müssen auch mithilfe ihrer Organisations-ID bei Office angemeldet sein) und über Exchange Online und aktive Exchange Online Postfächer verfügen. Ihr Abonnementverzeichnis muss sich entweder in Azure Active Directory befinden oder mit Azure Active Directory verbunden sein. 

Die Bereitstellung unterstützt Folgendes nicht: 

- Add-Ins, die Word, Excel oder PowerPoint in Office 2013 zum Ziel haben 
- Ein lokaler Verzeichnisdienst 
- Add-In-Bereitstellung in einem Exchange lokalen Postfach 
- Bereitstellung von COM-Add-Ins (Component Object Model) oder Visual Studio-Tools für Office-Add-Ins (VSTO). 
- Bereitstellungen von Microsoft 365, die keine Exchange Online enthalten, z. B. Microsoft 365 Apps for Business und Microsoft 365 Apps für Enterprise.  

### <a name="office-requirements"></a>Office Anforderungen 

Für Word-, Excel- und PowerPoint-Add-Ins müssen Ihre Benutzer eine der folgenden Optionen verwenden: 
- Auf einem Windows Gerät, Version 1704 oder höher von Microsoft 365 Enterprise Lizenzen (E3/E5/F3) oder Microsoft 365 Business-Lizenzen (Business Basic, Business Standard, Business Premium). 
- Auf einem Mac, Version 15.34 oder höher. 

Für Outlook müssen Ihre Benutzer eine der folgenden Optionen verwenden: 
- Version 1701 oder höher von Microsoft 365 Enterprise Lizenzen (E3/E5/F3) oder Microsoft 365 Business-Lizenzen (Business Basic, Business Standard, Business Premium). 
- Version 1808 oder höher von Office Professional Plus 2019 oder Office Standard 2019. 
- Version 16.0.4494.1000 oder höher von Office Professional Plus 2016 (MSI) oder Office Standard 2016 (MSI).
    > [!NOTE]
    > MSI-Versionen von Outlook zeigen vom Administrator installierte Add-Ins im entsprechenden Outlook-Menüband an, nicht im Abschnitt "Meine Add-Ins".  
- Version 15.0.4937.1000 oder höher von Office Professional Plus 2013 (MSI) oder Office Standard 2013 (MSI).
- Version 16.0.9318.1000 oder höher von Office 2016 für Mac. 
- Version 2.75.0 oder höher von Outlook Mobile für iOS. 
- Version 2.2.145 oder höher von Outlook Mobile für Android. 



### <a name="exchange-online-requirements"></a>Exchange Online-Anforderungen 
Microsoft Exchange speichert die Add-In-Manifeste im Mandanten Ihrer Organisation. Der Administrator, der Add-Ins bereitstellt, und die Benutzer, die diese Add-Ins erhalten, müssen sich auf einer Version von Exchange Online befinden, die die OAuth-Authentifizierung unterstützt. 

Informieren Sie sich beim Exchange-Administrator Ihrer Organisation, um herauszufinden, welche Konfiguration verwendet wird. Die OAuth-Konnektivität pro Benutzer kann mithilfe des [PowerShell-Cmdlets "Test-OAuthConnectivity"](/powershell/module/exchange/test-oauthconnectivity)überprüft   werden. 

### <a name="user-and-group-assignments"></a>Benutzer- und Gruppenzuordnungen
Die Bereitstellung des Add-Ins wird derzeit für die meisten von Azure Active Directory unterstützten Gruppen unterstützt, einschließlich Microsoft 365-Gruppen, Verteilerlisten und Sicherheitsgruppen. Die Bereitstellung unterstützt Benutzer in Gruppen auf oberster Ebene oder Gruppen ohne übergeordnete Gruppen, aber keine Benutzer in geschachtelten Gruppen oder Gruppen, die übergeordnete Gruppen haben. 

> [!NOTE]
> Nicht für E-Mail aktivierte Sicherheitsgruppen werden derzeit nicht unterstützt. 

Im folgenden Beispiel werden Scheit, Sheila und die Gruppe "Vertriebsabteilung" einem Add-In zugewiesen. Da es sich bei "Vertriebsabteilung Westküste" um eine geschachtelte Gruppe handelt, werden Bert und Fred keinem Add-In zugeordnet. 

![Diagramm der Vertriebsabteilung](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a>Herausfinden, ob eine Gruppe geschachelte Gruppen enthält

Die einfachste Methode, um herauszufinden, ob eine Gruppe geschachtelte Gruppen enthält, besteht darin, in Outlook die Gruppenvisitenkarte anzuzeigen. Wenn Sie den Gruppennamen im Feld **"An"**   einer E-Mail eingeben und dann bei der Auflösung den Gruppennamen auswählen, wird angezeigt, ob er Benutzer oder geschachtelte Gruppen enthält. Im folgenden Beispiel werden auf der Registerkarte **"Mitglieder"**   der Outlook-Visitenkarte für die Testgruppe keine Benutzer und nur zwei Untergruppen angezeigt. 

![Registerkarte "Mitglieder" der Outlook-Visitenkarte](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

Sie können die umgekehrte Abfrage durchführen, indem Sie die Gruppe auflösen, um zu sehen, ob sie Mitglied einer anderen Gruppe ist. Im folgenden Beispiel sehen Sie auf der Registerkarte <b>"Mitgliedschaft"</b>   der Outlook-Visitenkarte, dass Untergruppe 1 Mitglied der Testgruppe ist. 

![Registerkarte "Mitgliedschaft" der Outlook-Visitenkarte](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

Beachten Sie, dass Sie die Azure Active Directory Graph-API verwenden können, um Abfragen auszuführen, um die Liste der Gruppen innerhalb einer Gruppe zu finden. Weitere Informationen finden Sie unter [Vorgänge zu Gruppen | Graph-API-Referenz](/previous-versions/azure/ad/graph/api/groups-operations). 

## <a name="recommended-approach-for-deploying-office-add-ins"></a>Empfohlene Vorgehensweise für die Bereitstellung von Office-Add-Ins 
Zum Rollout von Add-Ins mithilfe eines stufenweisen Ansatzes empfehlen wir Folgendes: 
1. Stellen Sie das Add-In für eine kleine Gruppe von Projektbeteiligten und Mitgliedern der IT-Abteilung bereit. Sie können das Kennzeichen **aktivieren: Handelt es sich um eine Testbereitstellung.** Wenn die Bereitstellung erfolgreich ist, fahren Sie mit Schritt 2 fort. 

2. Stellen Sie das Add-In für weitere Personen innerhalb des Unternehmens bereit. Bewerten Sie erneut die Ergebnisse, und fahren Sie bei erfolgreicher Ausführung mit der vollständigen Bereitstellung fort. 

3. Durchführen eines vollständigen Rollouts für alle Benutzer. Deaktivieren Sie das Flag von **"Ist dies eine Testbereitstellung".** 

Je nach Größe der Zielgruppe können Sie Rolloutschritte hinzufügen oder entfernen.  

## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Bereitstellen eines Office-Add-Ins mithilfe des Admin Centers 

1. Wählen Sie im Admin Center **"Einstellungen"** und dann **"Integrierte Apps"** aus. 

2. Wählen Sie oben auf der Seite **"Apps abrufen"** aus. AppSource wird in einem eingebetteten Format geladen. Suchen Sie entweder nach einem Add-In, oder suchen Sie es, indem Sie im linken Navigationsbereich auf "Produkt" klicken.  Wenn das Add-In vom ISV mit einer SaaS-App oder anderen Apps und Add-Ins verknüpft wurde und die SaaS-App eine kostenpflichtige App ist, wird ihnen ein Dialogfeld angezeigt, in dem Sie die Lizenz erwerben oder bereitstellen können. Unabhängig davon, ob Sie die Lizenz erworben haben oder nicht, können Sie mit der Bereitstellung fortfahren. Wählen Sie **Bereitstellen**.  

3. Sie sehen die **Seite "Konfiguration",** auf der alle Apps aufgeführt sind. Wenn Sie nicht über Berechtigungen oder den richtigen Zugriff zum Bereitstellen der App verfügen, werden die entsprechenden Informationen hervorgehoben. Sie können die Apps auswählen, die Sie bereitstellen möchten. Wenn Sie **"Weiter"** auswählen, werden Sie die Seite **"Benutzer"** anzeigen. Wenn das Add-In nicht vom ISV verknüpft wurde, werden Sie zur Seite "Benutzer" weitergeleitet. 

4. Wählen Sie **"Jeder",** **"Bestimmte Benutzer/Gruppen"** oder **"Nur ich"**   aus, um anzugeben, für wen das Add-In bereitgestellt wird. Verwenden Sie das Suchfeld, um nach bestimmten Benutzern oder Gruppen zu suchen. Wenn Sie das Add-In testen, wählen Sie **"Ist dies eine Testbereitstellung"** aus. 

5. Wählen Sie **Weiter** aus. Alle App-Funktionen und -Berechtigungen werden in einem einzigen Bereich zusammen mit Zertifizierungsinformationen angezeigt, wenn die App über eine Microsoft 365-Zertifizierung verfügt. Wenn Sie das Zertifizierungslogo auswählen, können dem Benutzer weitere Details zur Zertifizierung angezeigt werden.  

6. Überprüfen Sie, und wählen Sie dann **"Bereitstellung fertig stellen"** aus.  

7. Ein grünes "Tick"-Symbol wird angezeigt, wenn das Add-In bereitgestellt wird. Befolgen Sie die Anweisungen auf der Seite, um das Add-In zu testen. 

> [!NOTE]
> Benutzer müssen Office möglicherweise neu starten, um das Add-In-Symbol auf dem App-Menüband anzuzeigen. Outlook-Add-Ins können bis zu 24 Stunden dauern, bis sie auf App-Menübändern angezeigt werden. 

Es empfiehlt sich, Benutzer und Gruppen darüber zu informieren, dass das bereitgestellte Add-In verfügbar ist. Erwägen Sie das Senden einer E-Mail, die beschreibt, wann und wie das Add-In verwendet wird. Einschließen oder Verknüpfen von Hilfeinhalten oder häufig gestellten Fragen, die Benutzern bei Problemen mit dem Add-In helfen können. 

## <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Überlegungen beim Zuweisen eines Add-Ins zu Benutzern und Gruppen 

Globale Administratoren und Exchange-Administratoren können jedem oder bestimmten Benutzern und Gruppen ein Add-In zuweisen. Jede Option hat Auswirkungen: 

- **Jeder**   Diese Option weist das Add-In jedem Benutzer in der Organisation zu. Verwenden Sie diese Option nur in Ausnahmefällen, da sie wirklich die gesamte Organisation betrifft. 

- **Benutzer**   Wenn Sie einem einzelnen Benutzer ein Add-In zuweisen und das Add-In dann für einen neuen Benutzer bereitstellen, müssen Sie zuerst den neuen Benutzer hinzufügen. 

- **Gruppen**   Wenn Sie einer Gruppe ein Add-In zuweisen, wird Benutzern, die der Gruppe hinzugefügt werden, automatisch das Add-In zugewiesen. Wenn ein Benutzer aus einer Gruppe entfernt wird, verliert der Benutzer den Zugriff auf das Add-In. In beiden Fällen ist keine zusätzliche Aktion vom Administrator erforderlich. 

- **Nur ich**   Wenn Sie ein Add-In nur sich selbst zuweisen, wird das Add-In nur Ihrem Konto zugewiesen, das ideal zum Testen des Add-Ins geeignet ist. 

Die richtige Option für Ihre Organisation hängt von Ihrer Konfiguration ab. Es wird jedoch empfohlen, Aufgaben mithilfe von Gruppen vorzunehmen. Als Administrator ist es möglicherweise einfacher, Add-Ins mithilfe von Gruppen zu verwalten und die Mitgliedschaft dieser Gruppen zu steuern, anstatt jedes Mal einzelne Benutzer zuzuweisen. In einigen Situationen können Sie den Zugriff auf eine kleine Gruppe von Benutzern einschränken, indem Sie bestimmten Benutzern Zuweisungen vornehmen, indem Sie Benutzer manuell zuweisen. 

### <a name="more-about-office-add-ins-security"></a>Weitere Informationen zur Sicherheit von Office-Add-Ins 
Office-Add-Ins sind eine Kombination aus einer XML-Manifestdatei, die einige Metadaten zum Add-In enthält, aber vor allem auf eine Webanwendung verweist, die den gesamten Code und die Logik enthält. Add-Ins können verschiedene Bereiche von Funktionen umfassen. So können Add-Ins beispielsweise Folgendes:
- Daten anzeigen. 
- Das Dokument eines Benutzers lesen, um kontextbezogene Dienste zur Verfügung zu stellen. 
- Daten im Dokument eines Benutzers lesen und in das Dokument schreiben, um diesem Benutzer einen Wert zu bieten.  

Weitere Informationen zu den Typen und Funktionen von Office-Add-Ins finden Sie in der Übersicht über die [Office-Add-Ins-Plattform,](/office/dev/add-ins/overview/office-add-ins)insbesondere im Abschnitt "Anatomie eines Office-Add-Ins". 

Um mit dem Dokument des Benutzers zu interagieren, muss das Add-In deklarieren, welche Berechtigung es im Manifest benötigt. Ein Fünf-Ebenen-JavaScript-API-Zugriffsberechtigungsmodell bietet die Basis für Datenschutz und Sicherheit für Benutzer von Aufgabenbereich-Add-Ins. Die Meisten der Add-Ins im Office Store sind auf "ReadWriteDocument" -Ebene, wobei fast alle Add-Ins mindestens die ReadDocument-Ebene unterstützen. Weitere Informationen zu den Berechtigungsstufen finden Sie unter [Anfordern von Berechtigungen für die API-Verwendung in Inhalts- und Aufgabenbereich-Add-Ins.](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins) 

Beim Aktualisieren eines Manifests werden in der Regel Änderungen am Symbol und Text eines Add-Ins vorgenommen. Gelegentlich ändern sich auch Add-In-Befehle. Die Berechtigungen des Add-Ins ändern sich jedoch nicht. Die Webanwendung, in der der gesamte Code und die Logik für das Add-In ausgeführt werden, kann sich jederzeit ändern. Dies liegt in der Natur von Webanwendungen. 

Aktualisierungen für Add-Ins werden auf folgende Weise ausgeführt: 
- **Branchen-Add-In:** In diesem Fall, in dem ein Administrator ein Manifest explizit hochgeladen hat, erfordert das Add-In, dass der Administrator eine neue Manifestdatei hochlädt, um Metadatenänderungen zu unterstützen. Beim nächsten Starten der jeweiligen Office-Anwendungen wird das Add-In aktualisiert. Die Webanwendung kann sich jederzeit ändern. 

- **Office Store-Add-In:** Wenn ein Administrator ein Add-In aus dem Office Store ausgewählt hat und ein Add-In im Office Store aktualisiert wird, wird das Add-In beim nächsten Start der entsprechenden Office-Anwendungen aktualisiert. Die Webanwendung kann sich jederzeit ändern. 

> [!NOTE]
> Verwenden Sie für Word, Excel und PowerPoint einen [SharePoint-App-Katalog,](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)   um Add-Ins für Benutzer in einer lokalen Umgebung ohne Verbindung zu Microsoft 365 und/oder Unterstützung für SharePoint-Add-Ins bereitzustellen. For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.  

## <a name="add-in-states"></a>Add-In-Status
Ein Add-In kann den Status **"Ein"**   oder **"Aus"**   aufweisen. 

| Status | Auftreten des Status | Auswirkung |
|:-----|:-----|:-----|
|**Aktiv**  <br/> |Der Administrator hat das Add-In hochgeladen und benutzern oder Gruppen zugewiesen.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen sehen es im jeweiligen Client.  <br/> |
|**Deaktiviert**  <br/> |Der Administrator hat das Add-In deaktiviert.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr auf das Add-In zugreifen.  <br/> Wenn der Zustand des Add-Ins in "Aktiv" geändert wird, können die Benutzer und Gruppen wieder darauf zugreifen.  <br/> |
|**Gelöscht**  <br/> |Der Administrator hat das Add-In gelöscht.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr darauf zugreifen.  <br/> |
 
Erwägen Sie das Löschen eines Add-Ins, wenn es nicht mehr verwendet wird. Beispielsweise kann das Deaktivieren eines Add-Ins sinnvoll sein, wenn ein Add-In nur zu bestimmten Zeiten des Jahres verwendet wird. 

## <a name="manage-an-office-add-in-using-the-admin-center"></a>Verwalten eines Office-Add-Ins mithilfe des Admin Centers

Nach der Bereitstellung können Administratoren auch den Benutzerzugriff auf Add-Ins verwalten. 

1. Wählen Sie im Admin Center **Einstellungen** und dann **integrierte Apps** aus. 
2. Auf der Seite "Integrierte Apps" wird eine Liste der Apps angezeigt, die entweder einzelne Add-Ins oder Add-Ins sind, die mit anderen Apps verknüpft wurden. 
3. Wählen Sie eine App mit **dem Status**    **"Weitere Verfügbare Apps"**   aus, um den Bereich **"Verwalten"** zu   öffnen. Der Status **weiterer verfügbarer Apps** teilt Ihnen   mit, dass es mehr Integrationen von den ISVs gibt, die noch nicht bereitgestellt wurden. 
4. Wählen Sie **auf** der Registerkarte   "Übersicht" die Option **"Bereitstellen" aus.** Einige Apps erfordern, dass Sie Benutzer hinzufügen, bevor Sie "Bereitstellen" auswählen können. 
5. Wählen Sie **"Benutzer",** **"Ist dies eine Testbereitstellung"** aus, und wählen Sie dann entweder **"Gesamte Organisation",** **"Bestimmte Benutzer/Gruppen"**   oder **"Nur ich"** aus. Sie können auch **"Testbereitstellung"**   auswählen, wenn Sie warten möchten, bis die App für die gesamte Organisation bereitgestellt wird. Bestimmte Benutzer oder Gruppen können eine Microsoft 365 Gruppe, eine Sicherheitsgruppe oder eine Verteilergruppe sein. 
6. Wählen Sie  **"Aktualisieren"**   und dann **"Fertig"** aus. Sie können jetzt auf der Registerkarte **"Übersicht"** die Option **"Bereitstellen"** auswählen. 
7. Überprüfen Sie die App-Informationen, und wählen Sie dann **Bereitstellen aus.**
8. Wählen Sie auf der Seite "Bereitstellung abgeschlossen" die Option **"Fertig"** aus, und überprüfen Sie   die Details des Tests oder der vollständigen Bereitstellung auf der Registerkarte   ****   "Übersicht". 
9. Wenn die App den Status  **"Update ausstehend"** aufweist, können Sie auf die App klicken, um den **Bereich "Verwalten"** zu öffnen und die App zu aktualisieren. 
10. Um nur Benutzer zu aktualisieren, wählen Sie die Registerkarte **"Benutzer" aus,** und nehmen Sie die entsprechende Änderung vor. Wählen Sie **"Aktualisieren"** aus, nachdem Sie Ihre Änderungen vorgenommen haben.  

## <a name="delete-an-add-in"></a>Löschen eines Add-Ins

Sie können auch ein Add-In löschen, das bereitgestellt wurde.

1. Wählen Sie im Admin Center **Einstellungen** und dann **integrierte Apps** aus.
2. Wählen Sie eine beliebige Zeile aus, um den Verwaltungsbereich anzuzeigen. 
3. Wählen Sie die Registerkarte **"Konfiguration" aus.** 
4. Wählen Sie das Add-In aus, das Sie löschen möchten, und wählen Sie dann **"Entfernen" aus.**  

> [!NOTE]
>  Wenn das Add-In von einem anderen Administrator bereitgestellt wurde, wird die Schaltfläche "Entfernen" deaktiviert. Nur der Administrator, der die App bereitgestellt hat, oder ein globaler Administrator kann das Add-In löschen.

## <a name="scenarios-where-exchange-admin-cannot-deploy-an-add-in"></a>Szenarien, in denen Exchange Administrator ein Add-In nicht bereitstellen kann 

Es gibt zwei Fälle, in denen ein Exchange Administrator kein Add-In bereitstellen kann:
- Wenn ein Add-In die Berechtigung für MS Graph APIs benötigt und die Zustimmung eines globalen Administrators benötigt.
- Wenn ein Add-In mit zwei oder mehr Add-Ins und Webapps verknüpft ist und mindestens eines dieser Add-Ins von einem anderen Administrator (Exchange/Global) bereitgestellt wird und die Benutzerzuweisung nicht einheitlich ist. Die Bereitstellung von Add-Ins wird nur zugelassen, wenn die Benutzerzuweisung für alle bereits bereitgestellten Apps identisch ist.  


## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>Welche Administratorrolle muss ich für den Zugriff auf integrierte Apps verwenden?

Nur globale Administratoren können auf integrierte Apps zugreifen. Integrierte Apps werden für andere Administratoren nicht im linken Navigationsbereich angezeigt.

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>Warum wird das Add-In im linken Navigationsbereich unter "Einstellung", aber nicht "Integrierte Apps" angezeigt?

Es kann einige Gründe geben:

- Der angemeldete Administrator ist ein Exchange Administrator.
- Der Kunde befindet sich in einer unabhängigen Cloud, und integrierte Apps sind für unabhängige Cloudkunden noch verfügbar.

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>Welche Apps kann ich über integrierte Apps bereitstellen?

Integrierte Apps ermöglichen die Bereitstellung von Web Apps, Teams App, Excel, PowerPoint, Word, Outlook-Add-Ins und SPFx Apps. Bei Add-Ins unterstützen integrierte Apps die Bereitstellung für Exchange Onlinepostfächer und nicht für lokale Exchange Postfächer.

### <a name="can-administrators-delete-or-remove-apps"></a>Können Administratoren Apps löschen oder entfernen?

Ja. Globale Administratoren können Apps löschen oder entfernen.

- Wählen Sie eine App aus der Listenansicht aus. Wählen Sie auf der Registerkarte **"Konfiguration"** aus, welche Apps entfernt werden sollen.  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>Sind integrierte Apps in der unabhängigen Cloud verfügbar?

Nein. Integrierte Apps sind für unabhängige Cloudkunden nicht verfügbar.

### <a name="is-integrated-apps-available-in-government-clouds"></a>Sind integrierte Apps in Government Clouds verfügbar?

Nein. Integrierte Apps sind für Government Cloud-Kunden nicht verfügbar.
