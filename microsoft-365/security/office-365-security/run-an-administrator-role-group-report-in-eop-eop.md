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
description: Administratoren erfahren, wie Sie einen Administratorrollegruppenbericht in eigenständigem Exchange Online Protection (EOP) ausführen. Dieser Bericht protokolliert, wenn ein Administrator Mitglieder zu Administratorrollegruppen hinzufügt oder aus diesen entfernt.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0281dcb13f5cee0ba8db8c4faed5054f481337cf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908794"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Ausführen eines Administrator-Rollengruppenberichts in EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection eigenständig](exchange-online-protection-overview.md)

In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer protokolliert der Dienst jedes Vorkommen, wenn ein Administrator Mitglieder zu administrativen Rollengruppen hinzufügt oder aus diesen entfernt. Weitere Informationen zu Rollengruppen in eigenständigem EOP finden Sie unter [Permissions in standalone EOP](feature-permissions-in-eop.md).

Wenn Sie einen Administratorrollegruppenbericht im Exchange Admin Center (EAC) ausführen, werden Einträge als Suchergebnisse angezeigt und enthalten die betroffenen Rollengruppen, die die Rollengruppenmitgliedschaft geändert haben und wann und welche Mitgliedschaftsupdates vorgenommen wurden. Mithilfe dieses Berichts können Sie Änderungen an den Administratorberechtigungen überwachen, die den Benutzern in der Organisation zugewiesen sind.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Öffnen des Exchange Admin Centers finden Sie unter [Exchange Admin Center im eigenständigen EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online Protection die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie  die Rolle Überwachungsprotokolle oder **Nur-Ansicht-Überwachungsprotokolle,** die  standardmäßig den Rollengruppen Organisationsverwaltung, Complianceverwaltung und Sicherheitsadministrator zugewiesen sind.  Weitere Informationen finden Sie unter [Permissions in standalone EOP](feature-permissions-in-eop.md) und [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter [Tastenkombinationen für](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)das Exchange Admin Center in Exchange Online .

> [!TIP]
> Liegt ein Problem vor? Bitten Sie im [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)-Forum um Hilfe.

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Ausführen eines Administrator-Rollengruppenberichts mithilfe der Exchange-Verwaltungskonsole

Führen Sie den Administratorrollegruppenbericht aus, um die Änderungen an Verwaltungsrollegruppen innerhalb eines bestimmten Zeitrahmens zu finden.

1. Wechseln Sie in der EAC zu **Complianceverwaltungsüberwachung,** und wählen Sie \>  **dann Administratorrollegruppenbericht ausführen aus.**

2. Konfigurieren Sie auf der Seite Nach **Änderungen an Administratorrollegruppen** suchen die folgenden Einstellungen:

   - **Startdatum** und **Enddatum**: Geben Sie einen Datumsbereich ein. Standardmäßig sucht der Bericht nach Änderungen, die innerhalb der letzten zwei Wochen an Administratorrollengruppen vorgenommen wurden.

   - **Rollengruppen auswählen:** Standardmäßig werden alle Rollengruppen durchsucht. Klicken Sie auf Rollengruppen auswählen, um die Ergebnisse nach bestimmten **Rollengruppen zu filtern.** Wählen Sie im angezeigten Dialogfeld eine Rollengruppe aus, und klicken Sie **auf Hinzufügen ->**. Wiederholen Sie diesen Schritt so oft wie erforderlich, und klicken Sie dann auf **OK,** wenn Sie fertig sind.

3. Klicken Sie nach Abschluss des Abschlusses auf **Suchen**.

Wenn Änderungen gefunden werden, die mit den angegebenen Kriterien übereinstimmen, werden sie im Ergebnisbereich angezeigt. Klicken Sie auf eine Rollengruppe in den Suchergebnissen, um die Änderungen im Detailbereich anzuzeigen.

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Wenn Sie einen Administrator-Rollengruppenbericht erfolgreich ausgeführt haben, werden die Rollengruppen, die innerhalb des Datumsbereichs geändert wurden, im Suchergebnisbereich angezeigt. Wenn keine Ergebnisse angezeigt werden, wurden im angegebenen Datumsbereich keine Änderungen an Rollengruppen vorgenommen. Wenn Sie davon ausgehen, dass Ergebnisse angezeigt werden sollten, ändern Sie den Datumsbereich, und führen Sie den Bericht erneut aus.

## <a name="monitor-changes-to-role-group-membership"></a>Überwachen von Änderungen an der Rollengruppenmitgliedschaft

Wenn einer Rollengruppe Mitglieder hinzugefügt oder daraus entfernt werden, wird in den im Detailbereich angezeigten Suchergebnissen angegeben, dass die Rollengruppenmitgliedschaft aktualisiert wurde, und die aktuellen Mitglieder werden aufgelistet. In den Ergebnissen ist nicht angegeben, welcher Benutzer hinzugefügt oder entfernt wurde.

Wenn Sie ermitteln möchten, ob ein Benutzer hinzugefügt oder entfernt wurde, müssen zwei separate Einträge im Bericht verglichen werden. Sehen Sie sich beispielsweise die folgenden Protokolleinträge für die Rollengruppe **HelpDesk** an:

> 27.01.2018 16:43 <br> Administrator <br> Aktualisierte Mitglieder: Administrator;annb,florencef;pilarp <br> 06.02.2018 10:09 <br> Administrator <br> Aktualisierte Mitglieder: Administrator;annb;florencef;pilarp;tonip <br> 19.02.2018 14:12 <br> Administrator <br> Aktualisierte Mitglieder: Administrator;annb;florencef;tonip

In diesem Beispiel wurden mit dem Administratorbenutzerkonto folgende Änderungen vorgenommen:

- Am 06.02.2018 wurde die Benutzer-Tonip hinzugefügt.
- Am 19.02.2018 entfernten sie den Benutzer pilarp.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Verwenden der eigenständigen Exchange Online PowerShell zum Suchen nach Überwachungsprotokolleinträgen

Sie können Exchange Online PowerShell verwenden, um nach Überwachungsprotokolleinträgen zu suchen, die die angegebenen Kriterien erfüllen. Eine Liste der Suchkriterien finden Sie unter [Search-AdminAuditLog search criteria](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet). Dieses Verfahren verwendet das **Cmdlet Search-AdminAuditLog** und zeigt Suchergebnisse in Exchange Online PowerShell an. Dieses Cmdlet kann verwendet werden, wenn eine Ergebnismenge zurückgegeben werden muss, die die im Cmdlet **New-AdminAuditLogSearch** oder in den Überwachungsberichten der Exchange-Verwaltungskonsole definierten Grenzwerte überschreitet.

Verwenden Sie die folgende Syntax, um das Überwachungsprotokoll anhand angegebener Kriterien zu durchsuchen.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> Das Cmdlet **Search-AdminAuditLog** gibt standardmäßig maximal 1.000 Protokolleinträge zurück. Verwenden Sie _den Parameter ResultSize,_ um bis zu 250.000 Protokolleinträge anzugeben. Oder verwenden Sie den `Unlimited` Wert, um alle Einträge zurückzukehren.

In diesem Beispiel wird eine Suche nach allen Überwachungsprotokolleinträgen ausgeführt, welche die folgenden Kriterien erfüllen:

- **Startdatum**: 04.08.2018
- **Enddatum**: 03.10.2018
- **Benutzer-IDs**: `davids` `chrisd` , , `kima`
- **Cmdlets**: **Set-Mailbox**
- **Parameter**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

In diesem Beispiel werden Änderungen an einem bestimmten Postfach ermittelt. Dies ist bei der Problembehebung nützlich, oder wenn Sie Informationen für eine Untersuchung bereitstellen müssen. Die folgenden Kriterien werden verwendet:

- **Startdatum**: 01.05.2018
- **Enddatum**: 03.10.2018
- **Objekt-ID**: contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Wenn ihre Suche viele Protokolleinträge zurücksengt, wird empfohlen, das unter Verwenden von **Exchange Online PowerShell** bereitgestellte Verfahren zu verwenden, um nach Überwachungsprotokolleinträgen zu suchen und Ergebnisse weiter später in diesem Artikel an einen Empfänger zu senden. Bei dieser Vorgehensweise wird eine XML-Datei als E-Mail-Anlage an die angegebenen Empfänger gesendet, sodass die relevanten Daten einfacher extrahiert werden können.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Anzeigen der Details von Überwachungsprotokolleinträgen

Das **Cmdlet Search-AdminAuditLog** gibt die unter [Überwachungsprotokollinhalte beschriebenen Felder zurück.](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents) Zwei der zurückgegebenen Felder, **CmdletParameters** und **ModifiedProperties**, enthalten zusätzliche Informationen, die standardmäßig nicht angezeigt werden.

Führen Sie die folgenden Schritte aus, um die Inhalte der Felder **CmdletParameters** und **ModifiedProperties** anzuzeigen. Sie können auch das Verfahren unter Verwenden von **Exchange Online PowerShell** verwenden, um nach Überwachungsprotokolleinträgen zu suchen und Ergebnisse weiter später in diesem Artikel an einen Empfänger zu senden, um eine XML-Datei zu erstellen.

In dieser Vorgehensweise werden die folgenden Konzepte verwendet:

- [about_Arrays](/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](/powershell/module/microsoft.powershell.core/about/about_variables)

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