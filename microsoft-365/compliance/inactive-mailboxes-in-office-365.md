---
title: Übersicht über inaktive Postfächer
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
description: In diesem Artikel erfahren Sie, wie Sie Postfachinhalte für frühere Mitarbeiter beibehalten, indem Sie das Postfach in ein inaktives Postfach umwandeln. Sie können dies tun, indem Sie das Postfach in einem Beweissicherungsverfahren platzieren oder eine Microsoft 365-Aufbewahrungsrichtlinie auf das Postfach anwenden und dann das entsprechende Microsoft 365-Konto entfernen.
ms.openlocfilehash: 1e6851d628af861982d0447f6b592d4b1aa8bba5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637927"
---
# <a name="overview-of-inactive-mailboxes"></a>Übersicht über inaktive Postfächer

In Ihrer Organisation müssen möglicherweise die e-Mails der ehemaligen Mitarbeiter aufbewahrt werden, nachdem Sie die Organisation verlassen haben. Abhängig von den Aufbewahrungsanforderungen Ihrer Organisation müssen Sie möglicherweise Postfachinhalte für einige Monate oder Jahre nach Beendigung der Arbeit aufbewahren, oder Sie müssen möglicherweise den Postfachinhalt auf unbestimmte Zeit aufbewahren. Unabhängig davon, wie lange Sie e-Mails aufbewahren müssen, können Sie inaktive Postfächer erstellen, um das Postfach ehemaliger Mitarbeiter beizubehalten. 
  
## <a name="what-are-inactive-mailboxes"></a>Was sind inaktive Postfächer?

Wenn ein Mitarbeiter Ihre Organisation verlässt (oder ein längerer Abwesenheits beurlaub), können Sie Ihr Microsoft 365-Konto entfernen. Die Postfachdaten des Mitarbeiters werden 30 Tage lang aufbewahrt, nachdem das Konto entfernt wurde. Während dieses Zeitraums können Sie die Postfachdaten weiterhin wiederherstellen, indem Sie das Löschen des Kontos Aufhebung. Nach 30 Tagen werden die Daten endgültig entfernt.
  
Wenn Ihre Organisation jedoch Postfachinhalte für frühere Mitarbeiter aufbewahren muss, können Sie das Postfach in ein inaktives Postfach umwandeln, indem Sie das Beweissicherungsverfahren für das Postfach aktivieren oder eine Microsoft 365-Aufbewahrungsrichtlinie auf das Postfach im Security & Compliance Center und dann auf das entsprechende Microsoft 365-Konto anwenden. Die Inhalte eines inaktiven Postfachs werden für die Dauer des beweissicherungsverfahrens für das Postfach oder den Aufbewahrungszeitraum der auf ihn angewendeten Aufbewahrungsrichtlinie aufbewahrt, bevor das Postfach gelöscht wurde. Sie können das entsprechende Benutzerkonto innerhalb eines Zeitraums von 30 Tagen wiederherstellen. Nach 30 Tagen wird das inaktive Postfach jedoch in Microsoft 365 aufbewahrt, bis die Aufbewahrungs-oder Aufbewahrungsrichtlinie entfernt wird. 
  
> [!IMPORTANT]
> Da wir weiterhin auf verschiedene Arten investieren, um Postfachinhalte beizubehalten, kündigen wir den Ruhestand von in-Place-Speicher in der Exchange-Verwaltungskonsole an. Das heißt, Sie sollten Beweissicherungsverfahren und Microsoft 365-Aufbewahrungsrichtlinien verwenden, um ein inaktives Postfach zu erstellen. Ab dem 1. Juli 2020 können Sie in Exchange Online keine neuen in-Place-Aufbewahrungsorte erstellen. Sie können jedoch weiterhin die Aufbewahrungsdauer eines in-situ-Speichers ändern, der in einem inaktiven Postfach platziert wird. Ab dem 1. Oktober 2020 können Sie die Aufbewahrungsdauer jedoch nicht ändern. Sie können ein inaktives Postfach nur löschen, indem Sie den in-situ-Speicher entfernen. Vorhandene inaktive Postfächer, die sich im Compliance-Archiv befinden, werden weiterhin beibehalten, bis die Aufbewahrung aufgehoben wird. Weitere Informationen darüber, wann in-Place-Speicher ausgemustert werden, finden Sie unter [Retirement of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).
  
## <a name="inactive-mailboxes-and-microsoft-365-retention-policies"></a>Inaktive Postfächer und Microsoft 365-Aufbewahrungsrichtlinien

Zusätzlich zum Beweissicherungsverfahren ist die Verwendung des neuen Microsoft 365-Aufbewahrungsrichtlinien Features im Security & Compliance Center eine weitere Möglichkeit, ein Postfach inaktiv zu machen. Um ein Postfach mithilfe einer Aufbewahrungsrichtlinie als inaktiv festzulegen, müssen Sie wie folgt vorgehen: 
  
- Es muss so konfiguriert werden, dass Inhalte beibehalten oder beibehalten und dann gelöscht werden. Wenn eine Aufbewahrungsrichtlinie so konfiguriert ist, dass nur Inhalte gelöscht werden, wird ein Postfach, auf das die Richtlinie angewendet wird, nicht inaktiv, wenn das Postfach gelöscht wird.

- Die Richtlinie muss auf Exchange-Postfächer oder Skype for Business-Speicherorte angewendet werden (da Skype-bezogene Inhalte im Postfach des Benutzers gespeichert werden). 
    
- Sie kann abfragebasiert sein, sodass nur Elemente aufbewahrt werden, die einer Suchabfrage entsprechen. 
    
Weitere Informationen zum Konfigurieren von Aufbewahrungsrichtlinien finden Sie unter [Overview of Retention Policies](retention-policies.md).
  
Wenn Sie eine Aufbewahrungsrichtlinie verwenden, um ein inaktives Postfach zu erstellen, wird von Microsoft 365 weiterhin die Aufbewahrungsrichtlinie für das inaktive Postfach verarbeitet. Dies bedeutet Folgendes: Wenn die Aufbewahrungsrichtlinie so konfiguriert ist, das Inhalte aufbewahrt und anschließend gelöscht werden, werden Elemente in den Ordner „Wiederherstellbare Elemente" verschoben, wenn die Aufbewahrungsdauer abläuft, und schließlich aus dem inaktiven Postfach gelöscht. Wenn die Aufbewahrungsrichtlinie nicht für gelöschte Elemente konfiguriert ist, werden Elemente, die nicht dauerhaft vom Benutzer gelöscht wurden (bevor das Postfach inaktiv gemacht wurde), nicht in den Ordner "Wiederherstellbare Elemente" verschoben und werden unbegrenzt aufbewahrt, nachdem das Postfach inaktiv geworden ist. 
  
Möglicherweise sollten Sie eine Microsoft 365-Aufbewahrungsrichtlinie speziell für inaktive Postfächer erstellen. Hier sind einige Gründe dafür und Punkte, die Sie beachten sollten.
  
- Sie können die Aufbewahrungsrichtlinie so konfigurieren, dass Postfachinhalte nur so lange aufbewahrt werden, wie erforderlich ist, um die Anforderungen Ihrer Organisation in Bezug auf ehemalige Mitarbeiter zu erfüllen.
    
- Es ist eine gute Möglichkeit, inaktive Postfächer zu identifizieren, da die Aufbewahrungsrichtlinie nur auf inaktive Postfächer angewendet wird.
    
- Sie können die Aufbewahrungsrichtlinie, die inaktiven Postfächern in Ihrer Organisation zugewiesen ist, schnell identifizieren. Auf diese Weise können Sie die Aufbewahrungseinstellungen (oder Löschungen) bei Bedarf einfacher ändern. Außerdem ist es einfacher, ein inaktives Postfach endgültig zu löschen, da Sie es mithilfe des Security & Compliance Center aus der Richtlinie entfernen können. Andernfalls müssen Sie Exchange Online PowerShell verwenden, um ein Beweissicherungsverfahren aus einem inaktiven Postfach zu entfernen, oder verwenden Sie Security & Compliance Center PowerShell, um ein inaktives Postfach aus einer organisationsweiten Microsoft 365-Aufbewahrungsrichtlinie auszuschließen.
    
- Wenn Sie eine Microsoft 365-Aufbewahrungsrichtlinie speziell für inaktive Postfächer erstellen, können Sie der Richtlinie maximal 1.000 Postfächer hinzufügen. Wenn Sie eine große Organisation sind, müssen Sie möglicherweise mehr als eine Microsoft 365-Aufbewahrungsrichtlinie für inaktive Postfächer erstellen.

> [!CAUTION]
> Wenn Sie eine Aufbewahrungsrichtlinie verwenden, um ein Postfach inaktiv zu machen, ändern oder entfernen Sie den Benutzerprinzipalnamen (User Principal Name, UPN) für das Postfach nicht, bevor Sie das entsprechende Benutzerkonto löschen. Ändern Sie außerdem nicht die primäre SMTP-Adresse (die vom UPN abgeleitet ist), oder entfernen Sie diese e-Mail-Adresse aus der Liste der sekundären SMTP-Adressen, die dem Postfach zugeordnet sind, bevor Sie das Postfach inaktiv machen. Wenn Sie die UPN-oder e-Mail-Adressen ändern (die dem Postfach zugewiesen wurden, als die Aufbewahrungsrichtlinie angewendet wurde), und dann das Benutzerkonto löschen, um das Postfach inaktiv zu machen, können Sie das inaktive Postfach nicht löschen, wenn Sie es nicht mehr beibehalten müssen. Das liegt daran, dass Sie das inaktive Postfach nicht mithilfe eines UPN oder einer e-Mail-Adresse (zur Identifizierung des inaktiven Postfachs) aus der Aufbewahrungsrichtlinie entfernen können, die sich von denen unterscheidet, die beim anfänglichen anwenden der Aufbewahrungsrichtlinie auf das Postfach vorhanden waren. Weitere Informationen zum Löschen inaktiver Postfächer finden Sie unter [Löschen eines inaktiven Postfachs in Office 365](delete-an-inactive-mailbox.md).
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Inaktive Postfächer und eDiscovery-Fallspeicher

Wenn ein Haltestatus, der einem eDiscovery-Fall im Security & Compliance Center zugeordnet ist, in einem Postfach gespeichert wird und das Postfach oder das Konto des Benutzers gelöscht wird, wird das Postfach zu einem inaktiven Postfach. Die Verwendung von eDiscovery-Fallspeichern zum Festlegen eines Postfachs als inaktiv wird jedoch nicht empfohlen. Grund hierfür ist, dass eDiscovery-Fälle für bestimmte zeitgebundene Fälle im Zusammenhang mit einem rechtlichen Problem vorgesehen sind. An einem bestimmten Punkt wird ein Rechtsfall wahrscheinlich enden, die dem Fall zugeordneten Speicherverfahren werden entfernt, und der eDiscovery-Fall wird geschlossen. Wenn ein für ein inaktives Postfach festgelegtes Speicherverfahren einem eDiscovery-Fall zugeordnet ist und das Speicherverfahren anschließend aufgehoben oder der eDiscovery-Fall geschlossen (oder gelöscht) wird, wird das inaktive Postfach endgültig gelöscht. Außerdem können Sie keinen zeitbasierten eDiscovery-Haltebereich erstellen. Das bedeutet, dass Inhalte in einem inaktiven Postfach für immer aufbewahrt werden oder bis das Archiv entfernt wird und das inaktive Postfach gelöscht wird. Daher wird empfohlen, ein Beweissicherungsverfahren oder eine Aufbewahrungsrichtlinie für inaktive Postfächer zu verwenden.
  
Weitere Informationen zu eDiscovery-Fällen und-Haltestatus finden Sie unter [eDiscovery Cases](ediscovery-cases.md).

## <a name="inactive-mailboxes-and-labels"></a>Inaktive Postfächer und Bezeichnungen

Beschriftungen unterstützen Sie beim Klassifizieren von e-Mail-Daten in Ihrer Organisation für die Steuerung und durchsetzen von Aufbewahrungsregeln basierend auf dieser Klassifizierung. Eine Bezeichnung kann entweder manuell von Benutzern oder automatisch von Administratoren auf ein E-Mail-Element angewendet werden, und einem E-Mail-Element kann nur eine Bezeichnung zugewiesen werden. Wenn einem einzelnen e-Mail-Element im Postfach eines Benutzers eine Bezeichnung zugewiesen ist (und es so konfiguriert ist, dass das Element beibehalten oder beibehalten und dann gelöscht wird), und das Postfach oder das Konto des Benutzers gelöscht wird, wird das Postfach zu einem inaktiven Postfach. Ähnlich wie bei eDiscovery-Fallspeichern wird auch die Verwendung von Bezeichnungen nicht empfohlen, um ein Postfach als inaktiv festzulegen. Stattdessen wird empfohlen, ein Beweissicherungsverfahren oder eine Aufbewahrungsrichtlinie zu verwenden. Im Fall von Beschriftungen erkennen Sie möglicherweise nicht, dass eine Bezeichnung auf ein e-Mail-Element angewendet wurde und dann versehentlich ein inaktives Postfach erstellen, wenn Sie das Konto des Benutzers löschen. 
  
Weitere Informationen über Bezeichnungen finden Sie unter [Übersicht über Bezeichnungen](labels.md).
  
## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>Inaktive Postfächer und automatisch expandierende Archive

Ein inaktives Postfach, das mit einem automatisch expandierenden Archiv konfiguriert ist, kann nicht wiederhergestellt oder wiederhergestellt werden. In Situationen, in denen die Wiederherstellung von Daten aus einem inaktiven Postfach mit einem automatisch wachsenden Archiv erforderlich ist, wird empfohlen, dass Sie das Inhalts Such Tool verwenden, um die Daten aus dem Postfach zu exportieren und dann in ein anderes Postfach zu importieren. Eine Schritt-für-Schritt-Anleitung zum Durchsuchen eines inaktiven Postfachs und zum Exportieren der Suchergebnisse finden Sie unter:

- [Inhaltssuche in Office 365](https://docs.microsoft.com/microsoft-365/compliance/content-search)

- [Exportieren von Inhalts Suchergebnissen](https://docs.microsoft.com/microsoft-365/compliance/export-search-results)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Inaktive Postfächer und Exchange MRM-Aufbewahrungsrichtlinien

Wenn eine Exchange-Aufbewahrungsrichtlinie (die Messaging-Datensatzverwaltung oder MRM-Funktion in Exchange Online) auf das Postfach angewendet wurde, als diese inaktiv wurde, werden alle Löschrichtlinien (die mit einer **Lösch** Aufbewahrungsaktion konfigurierte Aufbewahrungstags) für das inaktive Postfach weiterverarbeitet werden. Mit einer Löschrichtlinie markierte Elemente werden demnach in den Ordner „Wiederherstellbare Elemente" verschoben, wenn der Aufbewahrungszeitraum abläuft. Diese Elemente werden aus dem inaktiven Postfach gelöscht, wenn die Aufbewahrungsdauer abläuft. Wenn keine Aufbewahrungsdauer für das inaktive Postfach angegeben wurde, werden Elemente im Ordner „Wiederherstellbare Elemente" unbegrenzt aufbewahrt. 
  
Umgekehrt werden einem inaktiven Postfach zugewiesene Archivrichtlinien (mit der Aufbewahrungsaktion **MoveToArchive** konfigurierte Aufbewahrungstags) ignoriert, die in der Aufbewahrungsrichtlinie enthalten sind. Elemente in einem inaktiven Postfach, die mit einer Archivrichtlinie markiert sind, verbleiben demnach im primären Postfach, wenn die Aufbewahrungsdauer abläuft. Sie werden nicht in das Archivpostfach oder in den Ordner „Wiederherstellbare Elemente" im Archivpostfach verschoben. Sie werden unbegrenzt aufbewahrt. 
  
## <a name="creating-an-inactive-mailbox"></a>Erstellen eines inaktiven Postfachs

Damit ein Postfach inaktiv ist, muss ihm eine Exchange Online Plan 2-Lizenz (oder eine Exchange Online Plan 1-Lizenz mit einer Exchange Online-Archivierungs-Add-on-Lizenz) zugewiesen sein, damit ein Beweissicherungsverfahren oder eine Microsoft 365-Aufbewahrungsrichtlinie auf das Postfach angewendet werden kann, bevor es gelöscht wird. Nachdem das Postfach gelöscht wurde, stehen ihm zugeordnete Exchange Online Lizenzen zur Verfügung, die einem neuen Benutzer zugewiesen werden können.
  
Die folgende Tabelle enthält eine Übersicht über das Verfahren, mit dem ein inaktives Postfach in verschiedenen Aufbewahrungsszenarios erstellt wird. Weitere Informationen finden Sie unter [Verwalten inaktiver Postfächer](create-and-manage-inactive-mailboxes.md).
  
|**Ziel**|**Vorgehensweise**|**Ergebnis**|
|:-----|:-----|:-----|
|Aufbewahren des Postfachinhalts für unbegrenzte Zeit, nachdem ein Mitarbeiter die Organisation verlassen hat  <br/> | Platzieren Sie das Postfach in einem Beweissicherungsverfahren, oder wenden Sie eine Microsoft 365-Aufbewahrungsrichtlinie (die für die Aufbewahrung von Inhalten konfiguriert ist) an das Postfach an.  <br/>  Geben Sie keine Aufbewahrungsdauer für das Beweissicherungsverfahren an, oder konfigurieren Sie die Aufbewahrungsrichtlinie nicht zum Löschen von Elementen. Alternativ können Sie eine Aufbewahrungsrichtlinie verwenden, die Elemente für immer aufbewahrt.  <br/>  Entfernen Sie das Microsoft 365-Konto des Benutzers.  <br/> |Der gesamte Inhalt des inaktiven Postfachs, einschließlich der Elemente im Ordner "Wiederherstellbare Elemente", wird unbegrenzt aufbewahrt.  <br/> |
|Aufbewahren des Postfachinhalts für einen bestimmten Zeitraum nach dem Ausscheiden des Mitarbeiters und anschließendes Löschen  <br/> | Wenden Sie eine Microsoft 365-Aufbewahrungsrichtlinie auf das Postfach an.  <br/>  Konfigurieren Sie die Aufbewahrungsrichtlinie so, dass Elemente beibehalten und dann gelöscht werden, wenn der Aufbewahrungszeitraum abgelaufen ist.  <br/>  Entfernen Sie das Microsoft 365-Konto des Benutzers.  <br/> |Wenn der Aufbewahrungszeitraum für ein Postfachelement abläuft, wird das Element in den Ordner "Wiederherstellbare Elemente" verschoben und dann endgültig aus dem inaktiven Postfach gelöscht, wenn der Aufbewahrungszeitraum für gelöschte Elemente (für Exchange-Postfächer) abgelaufen ist. Der Aufbewahrungszeitraum der Microsoft 365-Aufbewahrungsrichtlinie kann basierend auf dem ursprünglichen Datum, an dem ein Postfachelement empfangen oder erstellt wurde, oder nach der letzten Änderung konfiguriert werden.  <br/> |
   
**Hinweis:** Wenn bereits ein Beweissicherungsverfahren für ein Postfach festgelegt wurde oder wenn eine Microsoft 365-Aufbewahrungsrichtlinie (die zum beibehalten oder beibehalten und Löschen von Inhalten konfiguriert ist) bereits auf das Postfach angewendet wurde, müssen Sie lediglich das entsprechende Benutzerkonto löschen, um ein inaktives Postfach zu erstellen. 
  
## <a name="managing-inactive-mailboxes"></a>Verwalten inaktiver Postfächer

Nachdem Sie ein Postfach als inaktiv festgelegt haben, können Sie verschiedene Verwaltungsaufgaben für inaktive Postfächer ausführen.
  
- **Ändern der Aufbewahrungsdauer für ein inaktives Postfach** Nachdem ein Postfach deaktiviert wurde, können Sie die Aufbewahrungsdauer des beweissicherungsverfahrens oder der Microsoft 365-Aufbewahrungsrichtlinie ändern, die auf das inaktive Postfach angewendet wird. Eine schrittweise Anleitung finden Sie unter [Ändern der Aufbewahrungsdauer für ein inaktives Postfach](change-the-hold-duration-for-an-inactive-mailbox.md).

  > [!NOTE]
  > Andere Aufbewahrungsrichtlinien können nicht auf ein inaktives Postfach angewendet werden. Sie können nur die Aufbewahrungsdauer einer vorhandenen Aufbewahrungsrichtlinie ändern, die auf das inaktive Postfach angewendet wird.
    
- **Wiederherstellen eines inaktiven Postfachs** Wenn ein ehemaliger (oder für längere Zeit freigestellter) Mitarbeiter in Ihre Organisation zurückkehrt oder ein neuer Mitarbeiter eingestellt wird, der die Zuständigkeiten des ehemaligen Mitarbeiters übernimmt, können Sie den Inhalt des inaktiven Postfachs wiederherstellen. Wenn Sie ein inaktives Postfach wiederherstellen, wird das Postfach in ein neues Postfach konvertiert, der Inhalt und die Ordnerstruktur des inaktiven Postfachs werden beibehalten, und das Postfach ist mit einem neuen Benutzerkonto verknüpft. Nach der Wiederherstellung ist das inaktive Postfach nicht mehr vorhanden. Schritt-für-Schritt-Verfahren und Informationen dazu, was geschieht, wenn Sie ein inaktives Postfach wiederherstellen, finden Sie unter [Wiederherstellen eines inaktiven Postfachs](recover-an-inactive-mailbox.md).
    
- **Wiederherstellen eines inaktiven Postfachs** Wenn ein anderer Mitarbeiter die Aufgaben eines ehemaligen Mitarbeiters übernimmt oder eine andere Person Zugriff auf die Inhalte des inaktiven Postfachs benötigt, können Sie den Inhalt des inaktiven Postfachs in einem vorhandenen Postfach wiederherstellen (oder zusammenführen). Wenn Sie ein inaktives Postfach wiederherstellen, werden die Inhalte in ein anderes Postfach kopiert. Das inaktive Postfach wird beibehalten und bleibt ein inaktives Postfach. Das inaktive Postfach kann weiterhin mithilfe von eDiscovery-Tools durchsucht werden, dessen Inhalt kann in einem anderen Postfach wiederhergestellt werden, und es kann später wiederhergestellt oder gelöscht werden. Eine schrittweise Anleitung finden Sie unter [Wiederherstellen eines inaktiven Postfachs](restore-an-inactive-mailbox.md).
    
- **Löschen eines inaktiven Postfachs** Wenn Sie den Inhalt eines inaktiven Postfachs nicht mehr aufbewahren müssen, können Sie ihn dauerhaft löschen, indem Sie alle Haltestatus oder Microsoft 365-Aufbewahrungsrichtlinien entfernen, die auf das inaktive Postfach angewendet werden. Wenn ein Postfach vor mehr als 30 Tagen inaktiv gemacht wurde, wird es für die dauerhafte Löschung markiert, nachdem Sie den Haltebereich entfernt haben. Wenn das Postfach innerhalb der letzten 30 Tage inaktiv gemacht wurde, können Sie es erneut aktivieren, nachdem Sie die Aufbewahrungs-oder Aufbewahrungsrichtlinie entfernt haben. Eine schrittweise Anleitung finden Sie unter [Löschen eines inaktiven Postfachs](delete-an-inactive-mailbox.md).
