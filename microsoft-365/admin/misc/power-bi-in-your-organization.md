---
title: Power BI in Ihrer Organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- PWB150
ms.assetid: d7941332-8aec-4e5e-87e8-92073ce73dc5
ROBOTS: NOINDEX
description: Erfahren Sie mehr über Power BI und wie Benutzer in Ihrer Organisation diesen Business Analytics-Dienst verwenden können.
ms.openlocfilehash: cabe489915061a773c0faeb8687695f2672fe478
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399302"
---
# <a name="power-bi-in-your-organization"></a>Power BI in Ihrer Organisation

[] Diese Seite beschreibt, wie Benutzer in Ihrer Organisation Power BI für Office 365 verwenden können, und wie Sie steuern können, wie Ihre Organisation diesen Service erwirbt.
    
## <a name="what-is-power-bi"></a>Was ist Power BI?

Microsoft Power BI ermöglicht es den Benutzern, Daten zu visualisieren, Entdeckungen mit anderen zu teilen und auf eine neuartige, intuitive Weise zusammenzuarbeiten. Weitere Informationen hierzu finden Sie auf der [Power BI-Website](https://powerbi.microsoft.com/en-us/).
  
## <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Erfüllt Power BI nationale, regionale und branchenspezifische Compliance-Anforderungen?

Weitere Informationen zur Power BI-Konformität finden Sie im [Microsoft Trust Center](https://go.microsoft.com/fwlink/?LinkId=785324).
  
## <a name="how-do-users-sign-up-for-power-bi"></a>Wie können sich Benutzer für Power BI registrieren?

Als Administrator können Sie sich für Power BI auf der [Power BI-Website](https://powerbi.microsoft.com/en-us/) registrieren. Sie können sich auch über die Seite "Einkaufsdienste" im Microsoft 365 Admin Center registrieren. Administratoren, die sich für Power BI registriert haben, können Benutzerabonnementlizenzen für Benutzer zuweisen, die Zugriff erhalten sollen.
  
Darüber hinaus sind einzelne Benutzer in Ihrer Organisation möglicherweise in der Lage, sich über die [Power BI-Website](https://powerbi.microsoft.com/en-us/) für Power BI zu registrieren. Wenn sich ein Benutzer in Ihrer Organisation für Power BI registriert, wird diesem Benutzer automatisch eine Power BI-Lizenz zugewiesen.
  
## <a name="how-do-individual-users-in-my-organization-sign-up"></a>Wie können sich einzelne Benutzer aus meiner Organisation registrieren?

Es gibt drei Szenarien, die ggf. für die Benutzer in Ihrer Organisation in Betracht kommen:
  
### <a name="scenario-1-your-organization-already-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-already-has-an-microsoft-365-account"></a>Szenario 1: Ihre Organisation verfügt bereits über eine vorhandene Microsoft 365-Umgebung, und der Benutzer, der sich für Power BI registriert hat, verfügt bereits über ein Microsoft 365-Konto.

In diesem Szenario aktiviert Microsoft einfach den Plan für das Konto, wenn der Benutzer bereits über ein Firmen- oder Schulkonto für den Mandanten (z. B. contoso.com) verfügt, aber noch nicht auf Power BI zugreifen kann. Der Benutzer wird automatisch benachrichtigt, wie er den Power BI-Dienst verwenden kann.
  
### <a name="scenario-2-your-organization-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-doesnt-have-an-microsoft-365-account"></a>Szenario 2: Ihre Organisation verfügt über eine vorhandene Microsoft 365-Umgebung, und der Benutzer, der sich für Power BI registriert, verfügt über kein Microsoft 365-Konto.

In diesem Szenario verfügt der Benutzer über eine e-Mail-Adresse in der Domäne Ihrer Organisation (beispielsweise contoso.com), aber noch kein Microsoft 365-Konto. In diesem Fall kann der Benutzer sich für Power BI registrieren und erhält automatisch ein Konto. Dadurch kann der Benutzer auf den Power BI-Dienst zugreifen. Wenn beispielsweise ein Mitarbeiter namens Nancy Ihre geschäftliche e-Mail-Adresse verwendet (beispielsweise Nancy@contoso.com), um sich anzumelden, fügt Microsoft Nancy automatisch als Benutzer in der Contoso-Microsoft 365-Umgebung hinzu und aktiviert Power BI für dieses Konto.
  
### <a name="scenario-3-your-organization-does-not-have-a-microsoft-365-environment-connected-to-your-email-domain"></a>Szenario 3: Ihre Organisation verfügt nicht über eine Microsoft 365-Umgebung, die mit Ihrer e-Mail-Domäne verbunden ist.

Es gibt keine administrativen Aktionen, die Ihre Organisation unternehmen muss, um die Vorteile von Power BI zu nutzen.
  
> [!IMPORTANT]
> Wenn Ihre Organisation über mehrere e-Mail-Domänen verfügt und Sie es vorziehen, dass sich alle e-Mail-Adresserweiterungen in demselben Mandanten befinden, fügen Sie vor dem Erstellen des primären Mandanten alle e-Mail-Adress Domänen zu diesem Mandanten hinzu, bevor Benutzer ihren primären Mandanten erstellen. Es gibt keinen automatischen Mechanismus, um Benutzer nach der Erstellung über Mandanten hinweg zu migrieren. Weitere Informationen zu diesem Prozess finden Sie unter [Wenn ich mehrere Domänen habe, kann ich den Mandanten steuern, dem Benutzer hinzugefügt werden?](#if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to) weiter unten in diesem Artikel und [Hinzufügen einer Domäne zu Office 365](../setup/add-domain.md) online. 
  
## <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Wie ändert sich dadurch die Art und Weise, in der ich die Identitäten für Benutzer in meiner Organisation heute verwalte?

Wenn in Ihrer Organisation bereits eine Microsoft 365-Umgebung vorhanden ist und alle Benutzer in Ihrer Organisation über Microsoft 365-Konten verfügen, ändert sich die Identitätsverwaltung nicht.
  
Wenn in Ihrer Organisation bereits eine Microsoft 365-Umgebung vorhanden ist, aber nicht alle Benutzer in Ihrer Organisation über Microsoft 365-Konten verfügen, werden wir einen Benutzer im Mandanten erstellen und Lizenzen basierend auf der geschäftlichen oder schulischen e-Mail-Adresse des Benutzers zuweisen. Dies bedeutet, dass die Anzahl der von Ihnen verwalteten Benutzer zu einem bestimmten Zeitpunkt größer wird, wenn sich Benutzer in Ihrer Organisation für den Dienst registrieren.
  
Wenn Sie Ihr Verzeichnis lokal verwalten und Active Directory Federation Services (AD FS) verwenden, fügt Microsoft Ihrem Mandanten keine Benutzer hinzu. Dann erhalten Benutzer, die Ihrem Mandanten beizutreten versuchen, eine Nachricht, dass sie sich mit dem Administrator Ihrer Organisation in Verbindung setzen sollen.
  
Wenn Ihre Organisation nicht über eine Microsoft 365-Umgebung verfügt, die mit Ihrer e-Mail-Domäne verbunden ist, ändert sich keine Änderung bei der Verwaltung der Identität. Die Benutzer werden einem neuen Nur-Cloud-Benutzerverzeichnis hinzugefügt, und Sie können entscheiden, ob Sie sie als Mandantenadministrator verwalten möchten.
  
## <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Was ist der Prozess zum Verwalten eines Mandanten, der von Microsoft für meine Benutzer erstellt wurde?

Wenn ein Mandant von Microsoft erstellt wurde, können Sie diesen mit den folgenden Schritten übernehmen und verwalten:
  
1. Treten Sie dem Mandanten bei, indem Sie sich [für Power BI registrieren](https://go.microsoft.com/fwlink/?LinkId=522448). Verwenden Sie hierfür eine E-Mail-Adressdomäne, die der zu verwaltenden Mandantendomäne entspricht. Wenn Microsoft beispielsweise den Mandanten "contoso.com" erstellt hat, müssen Sie ihm mit einer E-Mail-Adresse beitreten, die mit "@contoso.com" endet. 
    
2. Übernehmen Sie die Administratorkontrolle durch Überprüfung des Domänenbesitzes: Sobald Sie sich im Mandanten befinden, können Sie sich selbst zur Administratorrolle heraufstufen, indem Sie den Domänenbesitz überprüfen. Führen Sie hierfür die folgenden Schritte aus.
 
::: moniker range="o365-worldwide"
   
3. Wechseln Sie zu [https://admin.microsoft.com](https://admin.microsoft.com).
 

::: moniker-end

::: moniker range="o365-germany"

3. Wechseln Sie zu [https://portal.office.de](https://portal.office.de).

::: moniker-end

::: moniker range="o365-21vianet"

3. Wechseln Sie zu [https://portal.partner.microsoftonline.cn](https://portal.partner.microsoftonline.cn).

::: moniker-end

    
4. Klicken Sie oben links auf das App-Startsymbol, und wählen Sie **Admin** aus.
    
    ![App-Startprogramm mit hervorgehobener admin-App](../../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
5. Lesen Sie die Anweisungen auf der Seite **Administrator werden** , und wählen Sie dann **Ja, ich möchte der Administrator sein**aus.
    
    > [!NOTE]
    >  Wenn diese Option nicht angezeigt wird, ist bereits ein Administrator vorhanden. 
  
## <a name="if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to"></a>Kann ich den Mandanten steuern, dem Benutzer hinzugefügt werden, wenn ich über mehrere Domänen verfüge?

Wenn Sie nichts unternehmen, wird ein Mandant für jede E-Mail-Domäne und -Unterdomäne für Benutzer erstellt.
  
Wenn sich alle Benutzer unabhängig von ihren E-Mail-Adresserweiterungen in demselben Mandanten befinden sollen, gehen Sie folgendermaßen vor:
  
- Erstellen Sie im Voraus einen Zielmandanten, oder verwenden Sie einen vorhandenen Mandanten, und fügen Sie alle vorhandenen Domänen und Unterdomänen hinzu, die in diesem Mandanten konsolidiert werden sollen. Dann treten alle Benutzer, deren E-Mail-Adressen auf diese Domänen und Unterdomänen enden, bei ihrer Registrierung dem Zielmandanten automatisch bei.
    
> [!IMPORTANT]
> Es gibt keinen unterstützten automatisierten Mechanismus zum mandantenübergreifenden Verschieben von Benutzern nach deren Erstellung. Informationen zum Hinzufügen von Domänen zu einem einzelnen Microsoft 365-Mandanten finden Sie unter [Hinzufügen einer Domäne zu Office 365](../setup/add-domain.md). 
  
> [!IMPORTANT]
> Weitere Informationen und Anleitungen zum Verwalten von Mandanten finden Sie unter [Was ist Power BI Administration?](https://docs.microsoft.com/power-bi/service-admin-administering-power-bi-in-your-organization). 
  
## <a name="how-can-i-prevent-users-from-joining-my-existing-tenant"></a>Wie kann ich verhindern, dass Benutzer meinem vorhandenen Mandanten beitreten?

Es gibt Schritte, die Sie als Administrator ausführen können, um zu verhindern, dass Benutzer Ihrem vorhandenen Mandanten beitreten. Wenn Sie dies blockieren, treten bei den Anmeldeversuchen der Benutzer ein Fehler auf, und Sie werden zur Kontaktaufnahme mit dem Administrator Ihrer Organisation aufgefordert. Sie müssen diesen Vorgang nicht wiederholen, wenn Sie die automatische Lizenz Verteilung bereits zuvor deaktiviert haben (beispielsweise Office 365 Ausbildung für Schüler, Dozenten und Mitarbeiter).
  
Für diese Schritte muss Windows PowerShell verwendet werden. Eine Einführung in Windows PowerShell finden Sie im Handbuch [Erste Schritte mit PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=286814).
  
Um die folgenden Schritte ausführen zu können, müssen Sie die neueste 64-Bit-Version des [PowerShell-Moduls Azure Active Directory v2](https://www.powershellgallery.com/packages/AzureADPreview/2.0.2.5)installieren.
  
Nachdem Sie den Link ausgewählt haben, wählen Sie **Ausführen** aus, um das Installationspaket auszuführen. 
  
 **Deaktivieren des automatischen Mandantenbeitritts**: Mit diesem Windows PowerShell-Befehl können Sie verhindern, dass neue Benutzer einem verwalteten Mandanten beitreten:
  
So deaktivieren Sie den automatischen Mandantenbeitritt für neue Benutzer:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`
  
So aktivieren Sie den automatischen Mandantenbeitritt für neue Benutzer:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
> [!NOTE]
> Diese Sperre hindert neue Benutzer in Ihrer Organisation daran, sich für Power BI zu registrieren. Benutzer, die sich vor dem Deaktivieren neuer Registrierungen für Ihre Organisation bei Power BI registriert haben, behalten ihre Lizenzen. Weitere Informationen finden Sie unter [wie entferne ich Power BI für Benutzer, die sich bereits registriert haben?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) Anweisungen dazu, wie Sie den Zugriff auf Power BI für Benutzer entfernen können, die sich zuvor für den Dienst angemeldet hatten. 
  
## <a name="how-can-i-allow-users-to-join-my-existing-tenant"></a>Wie kann ich Benutzern erlauben, meinem vorhandenen Mandanten beizutreten?

Wenn Sie es Benutzern ermöglichen möchten, Ihrem Mandanten beizutreten, führen Sie den gegenteiligen Befehl wie den in der vorstehenden Frage beschriebenen aus:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
## <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Wie überprüfe ich, ob eine Sperre im Mandanten vorliegt?

Verwenden Sie das folgende PowerShell-Skript:  `Get-MsolCompanyInformation | fl allow*`
  
## <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Wie kann ich verhindern, dass vorhandene Benutzer mit der Nutzung von Power BI beginnen?

 **Automatische Lizenz Verteilung deaktivieren:** Verwenden Sie dieses Windows PowerShell Skript, um automatische Lizenz Verteilung für vorhandene Benutzer zu deaktivieren. Sie müssen diesen Vorgang nicht wiederholen, wenn Sie die automatische Lizenz Verteilung bereits zuvor deaktiviert haben (beispielsweise Office 365 Ausbildung für Schüler, Dozenten und Mitarbeiter). 
  
So deaktivieren Sie die automatische Lizenzverteilung für vorhandene Benutzer:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`
  
So aktivieren Sie die automatische Lizenzverteilung für vorhandene Benutzer:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
> [!NOTE]
> Das *AllowAdHocSubscriptions* -Flag wird verwendet, um mehrere Benutzerfunktionen in Ihrer Organisation zu steuern, einschließlich der Möglichkeit für Benutzer, sich für den Azure Rights Management-Dienst zu registrieren. Das Ändern dieses Flags wirkt sich auf alle Benutzeroptionen aus. 
  
## <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Wie kann ich es meinen vorhandenen Benutzern ermöglichen, sich für Power BI zu registrieren?

Wenn Sie es Ihren vorhandenen Benutzern ermöglichen möchten, sich für Power BI zu registrieren, führen Sie den gegenteiligen Befehl wie den in der vorstehenden Frage beschriebenen aus:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
## <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Wie entferne ich Power BI für Benutzer, die sich bereits registriert haben?

Wenn ein Benutzer sich für Power BI registriert hat, Sie aber nicht möchten, dass diese Person weiterhin Zugriff auf Power BI hat, können Sie die Power BI-Lizenz für diesen Benutzer entfernen.

::: moniker range="o365-worldwide"

> [!NOTE]
> Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.
  
1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
    
2. Suchen Sie nach dem Benutzer, für den Sie die Lizenz entfernen möchten, und wählen Sie dann den Namen aus.
    
3. Deaktivieren Sie auf der Registerkarte **Lizenzen und apps** das Kontrollkästchen **Microsoft Power BI** .
    
4. Wählen Sie **Änderungen speichern** aus.

::: moniker-end

  
::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

2. Suchen Sie nach dem Benutzer, für den Sie die Lizenz entfernen möchten, und wählen Sie dann den Namen aus.
    
3. Wählen Sie neben **Produktlizenzen**die Option **Bearbeiten**aus. 
    
4. Schaltet die **Microsoft Power BI** -Option aus.
    
5. Klicken Sie auf **Speichern**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

2. Suchen Sie nach dem Benutzer, für den Sie die Lizenz entfernen möchten, und wählen Sie dann den Namen aus.
    
3. Wählen Sie neben **Produktlizenzen**die Option **Bearbeiten**aus. 
    
4. Schaltet die **Microsoft Power BI** -Option aus.
    
5. Wählen Sie **Speichern**.

::: moniker-end 


## <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Wie erfahre ich, wenn meinem Mandanten neue Benutzer beigetreten sind?

Benutzern, die Ihrem Mandanten im Rahmen dieses Programms beigetreten sind, wird eine eindeutige Lizenz zugewiesen, nach der Sie innerhalb Ihres aktiven Benutzerbereichs im Verwaltungsdashboard filtern können.
  
Um diese neue Ansicht zu erstellen, führen Sie im Admin Center die Schritte unter [Erstellen einer benutzerdefinierten Benutzeransicht](../add-users/create-edit-or-delete-a-custom-user-view.md#create-a-custom-user-view)aus. Wählen Sie unter **zugewiesene Produktlizenz**die Option **Microsoft Power BI**aus. Nachdem die neue Ansicht erstellt wurde, können Sie alle Benutzer in Ihrem Mandanten anzeigen, die sich für dieses Programm registriert haben.
  
## <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>Gibt es weitere Punkte, auf die ich vorbereitet sein sollte?

Möglicherweise wird die Anzahl der Anforderungen zum Zurücksetzen des Kennworts größer. Informationen zu diesem Vorgang finden Sie unter [Zurücksetzen eines Benutzerkennworts](../add-users/reset-passwords.md).
  
Sie können einen Benutzer aus Ihrem Mandanten über den Standardprozess im Admin Center entfernen. Wenn der Benutzer jedoch weiterhin über eine aktive E-Mail-Adresse aus Ihrer Organisation verfügt, kann er erneut beitreten, es sei denn, Sie sperren den Beitritt für alle Benutzer.
  
## <a name="why-did-1-million-licenses-for-microsoft-power-bi-show-up-in-my-tenant"></a>Warum wurden 1 Million Lizenzen für Microsoft Power BI in meinem Mandanten angezeigt?

Als qualifizierte Organisation können Benutzer in Ihrer Organisation den Microsoft Power BI-Dienst verwenden, und diese Lizenzen stellen die verfügbare Kapazität für neue Power BI-Benutzer in Ihrem Mandanten dar. Für diese Lizenzen fallen keine Gebühren an. Wenn Sie sich entschieden haben, Benutzern das Anmelden für Power BI selbst zu erlauben, wird Ihnen eine dieser verfügbaren freien Lizenzen zugewiesen, wenn Sie den Anmeldevorgang abschließen. Sie können auch festlegen, dass diese Lizenzen Benutzern selbst über das Admin Center zugewiesen werden sollen.
  
## <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Ist das kostenlos? Oder werden mir diese Lizenzen in Rechnung gestellt?

Diese Lizenzen sind für die kostenlose Version von Power BI vorgesehen. Wenn Sie an zusätzlichen Möglichkeiten interessiert sind, schauen Sie sich die Version Power BI Pro an.
  
## <a name="why-1-million-licenses"></a>Warum eine Million Lizenzen?

Wir haben eine Zahl ausgewählt, die groß genug war, dass die Mehrzahl der Organisationen über ausreichende Lizenzen verfügt, um diesen Vorteil Ihren Benutzern unverzüglich zur Verfügung zu stellen.
  
## <a name="what-if-i-need-more-than-1-million-licenses"></a>Was kann ich tun, wenn ich mehr als eine Million Lizenzen benötige?

Bitten Sie Ihren Microsoft-Kontobeauftragten um weitere Informationen, wenn Sie zusätzliche Lizenzen benötigen.
