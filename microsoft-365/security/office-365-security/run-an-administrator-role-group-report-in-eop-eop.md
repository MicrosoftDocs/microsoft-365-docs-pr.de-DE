---
title: Ausführen eines Administrator-Rollengruppenberichts in EOP als eigenständige Lösung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie einen Administrator-Rollengruppenbericht in eigenständigem Exchange Online Protection (EOP) ausführen. Dieser Bericht protokolliert, wenn ein Administrator Mitglieder zu Administrator-Rollengruppen hinzufügt oder aus diesen entfernt.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 507fbe6fb6c99677cf91b6eb824bf110f1c826f3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166627"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Ausführen eines Administrator-Rollengruppenberichts in EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection als eigenständige Lösung](https://go.microsoft.com/fwlink/?linkid=2148611)

Wenn ein Administrator in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer Mitglieder zu administrativen Rollengruppen hinzufügt oder aus diesen entfernt, protokolliert der Dienst jedes Vorkommen. Weitere Informationen zu Rollengruppen in eigenständigem EOP finden Sie unter ["Berechtigungen" in EOP als eigenständige Lösung.](feature-permissions-in-eop.md)

Wenn Sie einen Administrator-Rollengruppenbericht in der Exchange Admin Center (EAC) ausführen, werden Einträge als Suchergebnisse angezeigt und enthalten die betroffenen Rollengruppen, die Benutzer, die die Rollengruppenmitgliedschaft geändert haben und wann und welche Mitgliedschaftsaktualisierungen vorgenommen wurden. Mithilfe dieses Berichts können Sie Änderungen an den Administratorberechtigungen überwachen, die den Benutzern in der Organisation zugewiesen sind.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Öffnen des Exchange Admin Centers finden Sie im [Exchange Admin Center in EOP als eigenständige Lösung.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online Protection die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rolle **"Überwachungsprotokolle"** oder **"Nur-Anzeige-Überwachungsprotokolle",** die standardmäßig den Rollengruppen "Organisationsverwaltung", "Verwaltung der Richtlinienkonformität" und "Sicherheitsadministrator" zugewiesen sind.   Weitere Informationen finden Sie unter "Berechtigungen [in EOP als eigenständige](feature-permissions-in-eop.md) Lösung", und ändern Sie mithilfe der EAC die Liste der Mitglieder in [Rollengruppen.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter Tastenkombinationen für das [Exchange Admin Center in Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Liegt ein Problem vor? Bitten Sie im [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)-Forum um Hilfe.

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Ausführen eines Administrator-Rollengruppenberichts mithilfe der Exchange-Verwaltungskonsole

Führen Sie den Administrator-Rollengruppenbericht aus, um die Änderungen an Verwaltungsrollegruppen innerhalb eines bestimmten Zeitrahmens zu finden.

1. Wechseln Sie in der EAC zu **Überwachung** der Verwaltung der Richtlinienverwaltung, und wählen Sie dann \>  **"Administrator-Rollengruppenbericht ausführen" aus.**

2. Konfigurieren Sie **auf der Seite "Nach Änderungen an Administrator-Rollengruppen suchen",** die geöffnet wird, die folgenden Einstellungen:

   - **Startdatum** und **Enddatum**: Geben Sie einen Datumsbereich ein. Standardmäßig sucht der Bericht nach Änderungen, die innerhalb der letzten zwei Wochen an Administratorrollengruppen vorgenommen wurden.

   - **Rollengruppen auswählen:** Standardmäßig werden alle Rollengruppen durchsucht. Klicken Sie auf "Rollengruppen auswählen", um die Ergebnisse nach **bestimmten Rollengruppen zu filtern.** Wählen Sie im angezeigten Dialogfeld eine Rollengruppe aus, und klicken **Sie auf "Add->"**. Wiederholen Sie diesen Schritt so oft wie nötig, und klicken Sie dann auf **"OK",** wenn Sie fertig sind.

3. Wenn Sie fertig sind, klicken Sie auf **"Suchen".**

Wenn Änderungen gefunden werden, die mit den angegebenen Kriterien übereinstimmen, werden sie im Ergebnisbereich angezeigt. Klicken Sie auf eine Rollengruppe in den Suchergebnissen, um die Änderungen im Detailbereich anzuzeigen.

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Wenn Sie einen Administrator-Rollengruppenbericht erfolgreich ausgeführt haben, werden die Rollengruppen, die innerhalb des Datumsbereichs geändert wurden, im Suchergebnisbereich angezeigt. Wenn keine Ergebnisse angezeigt werden, wurden im angegebenen Datumsbereich keine Änderungen an Rollengruppen vorgenommen. Wenn Sie davon ausgehen, dass Ergebnisse angezeigt werden sollten, ändern Sie den Datumsbereich, und führen Sie den Bericht erneut aus.

## <a name="monitor-changes-to-role-group-membership"></a>Überwachen von Änderungen an der Rollengruppenmitgliedschaft

Wenn einer Rollengruppe Mitglieder hinzugefügt oder daraus entfernt werden, wird in den im Detailbereich angezeigten Suchergebnissen angegeben, dass die Rollengruppenmitgliedschaft aktualisiert wurde, und die aktuellen Mitglieder werden aufgelistet. In den Ergebnissen ist nicht angegeben, welcher Benutzer hinzugefügt oder entfernt wurde.

Wenn Sie ermitteln möchten, ob ein Benutzer hinzugefügt oder entfernt wurde, müssen zwei separate Einträge im Bericht verglichen werden. Sehen Sie sich beispielsweise die folgenden Protokolleinträge für die Rollengruppe **HelpDesk** an:

> 27.01.2018 16:43 <br> Administrator <br> Aktualisierte Mitglieder: Administrator;annb,florencef;pilarp <br> 06.02.2018 10:09 Uhr <br> Administrator <br> Aktualisierte Mitglieder: Administrator;annb;florencef;pilarp;tonip <br> 19.02.2018 14:12 <br> Administrator <br> Aktualisierte Mitglieder: Administrator;annb;florencef;tonip

In diesem Beispiel wurden mit dem Administratorbenutzerkonto folgende Änderungen vorgenommen:

- Am 06.02.2018 wurde der Benutzer tonip hinzugefügt.
- Am 19.02.2018 wurde der Benutzer "pilarp" entfernt.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Verwenden der eigenständigen Exchange Online PowerShell zum Suchen nach Überwachungsprotokolleinträgen

Sie können Exchange Online PowerShell verwenden, um nach Überwachungsprotokolleinträgen zu suchen, die den von Ihnen angegebenen Kriterien entsprechen. Eine Liste der Suchkriterien finden Sie unter [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet). Dieses Verfahren verwendet das **Cmdlet "Search-AdminAuditLog"** und zeigt Suchergebnisse in Exchange Online PowerShell an. Dieses Cmdlet kann verwendet werden, wenn eine Ergebnismenge zurückgegeben werden muss, die die im Cmdlet **New-AdminAuditLogSearch** oder in den Überwachungsberichten der Exchange-Verwaltungskonsole definierten Grenzwerte überschreitet.

Verwenden Sie die folgende Syntax, um das Überwachungsprotokoll anhand angegebener Kriterien zu durchsuchen.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> Das Cmdlet **Search-AdminAuditLog** gibt standardmäßig maximal 1.000 Protokolleinträge zurück. Verwenden Sie _den Parameter "ResultSize",_ um bis zu 250.000 Protokolleinträge anzugeben. Oder verwenden Sie den `Unlimited` Wert, um alle Einträge zurückzukehren.

In diesem Beispiel wird eine Suche nach allen Überwachungsprotokolleinträgen ausgeführt, welche die folgenden Kriterien erfüllen:

- **Startdatum:** 04.08.2018
- **Enddatum:** 03.10.2018
- **Benutzer-IDs:** `davids` `chrisd` , , `kima`
- **Cmdlets**: **Set-Mailbox**
- **Parameter**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

In diesem Beispiel werden Änderungen an einem bestimmten Postfach ermittelt. Dies ist bei der Problembehebung nützlich, oder wenn Sie Informationen für eine Untersuchung bereitstellen müssen. Die folgenden Kriterien werden verwendet:

- **Startdatum:** 01.05.2018
- **Enddatum:** 03.10.2018
- **Objekt-ID:** contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Wenn ihre Suche viele Protokolleinträge zurück gibt, wird empfohlen, das unter Exchange **Online PowerShell** beschriebene Verfahren zu verwenden, um nach Überwachungsprotokolleinträgen zu suchen und Ergebnisse später in diesem Artikel an einen Empfänger zu senden. Bei dieser Vorgehensweise wird eine XML-Datei als E-Mail-Anlage an die angegebenen Empfänger gesendet, sodass die relevanten Daten einfacher extrahiert werden können.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Anzeigen der Details von Überwachungsprotokolleinträgen

Das **Cmdlet Search-AdminAuditLog** gibt die in überwachungsprotokollinhalten [beschriebenen Felder zurück.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents) Zwei der zurückgegebenen Felder, **CmdletParameters** und **ModifiedProperties**, enthalten zusätzliche Informationen, die standardmäßig nicht angezeigt werden.

Führen Sie die folgenden Schritte aus, um die Inhalte der Felder **CmdletParameters** und **ModifiedProperties** anzuzeigen. Sie können auch das Verfahren in **Exchange Online PowerShell** verwenden, um nach Überwachungsprotokolleinträgen zu suchen und Ergebnisse später in diesem Artikel an einen Empfänger zu senden, um eine XML-Datei zu erstellen.

In dieser Vorgehensweise werden die folgenden Konzepte verwendet:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. Legen Sie die Suchkriterien fest, führen Sie das Cmdlet **Search-AdminAuditLog** aus, und speichern Sie die Ergebnisse über den folgenden Befehl in einer Variablen.

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. Jeder Überwachungsprotokolleintrag wird als Arrayelement in der Variablen `$Results` gespeichert. Zur Auswahl eines Arrayelements geben Sie den Arrayelementindex an. Arrayelementindizes beginnen für das erste Arrayelement bei 0. Verwenden Sie beispielsweise den folgenden Befehl, um das fünfte Arrayelement (mit dem Index 4) abzurufen.

   ```PowerShell
   $Results[4]
   ```

3. Der oben stehende Befehl gibt den im Arrayelement 4 gespeicherten Protokolleintrag zurück. Zum Anzeigen der Felder **CmdletParameters** und **ModifiedProperties** für diesen Protokolleintrag verwenden Sie die folgenden Befehle.

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. Um die Inhalte der Felder **CmdletParameters** und **ModifiedParameters** in einem anderen Protokolleintrag anzuzeigen, ändern Sie den Arrayelementindex.
