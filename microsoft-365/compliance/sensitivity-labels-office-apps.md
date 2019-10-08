---
title: Funktionsweise von Vertraulichkeitsbezeichnungen in Office-Apps
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Mit Vertraulichkeitsbezeichnungen können Sie Ihre vertraulichen Inhalte klassifizieren und schützen, ohne dass die Produktivität Ihrer Mitarbeiter und deren Fähigkeit zur Zusammenarbeit behindert wird. Mithilfe von Vertraulichkeitsbezeichnungen können Sie Schutzeinstellungen wie Verschlüsselung oder Wasserzeichen für bezeichnete Inhalte erzwingen.
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417564"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a>Funktionsweise von Vertraulichkeitsbezeichnungen in Office-Apps

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a>Welche Voraussetzungen gelten für die Verwendung von Vertraulichkeitsbezeichnungen in Office-Anwendungen?

### <a name="common-requirements"></a>Allgemeine Anforderungen 

- Einheitliche Vertraulichkeitsbezeichnungen müssen [im Security & Compliance Center konfiguriert und veröffentlicht werden](https://aka.ms/managemip).
- Benutzer müssen bei Office mit Ihrem Geschäftskonto angemeldet sein.
- Benutzer müssen über eine Lizenz für Office 365 E3 oder höher verfügen.

### <a name="additional-requirements-for-office-for-windows"></a>Zusätzliche Anforderungen für Office für Windows 

- Der Azure Information Protection-Client darf nicht in Office ausgeführt werden. Siehe auch: [Können Vertraulichkeitsbezeichnungen neben dem Azure Information Protection-Client in Office für Windows ausgeführt werden?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows)

### <a name="additional-requirements-for-outlook-on-all-platforms"></a>Zusätzliche Voraussetzungen für Outlook auf allen Plattformen 

- Wenn Sie in Ihrer Bezeichnungskonfiguration die Inhaltskennzeichnung aktivieren, müssen Sie Exchange Online verwenden, damit diese Inhaltskennzeichnung während der Übertragung eingefügt wird.

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a>Welche Funktionen im Zusammenhang mit Vertraulichkeitsbezeichnungen werden in Office heute unterstützt? 

<table border="1" cellspacing="0" cellpadding="0">
<th><font size="-1">Funktion<th><font size="-1">Windows<th><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</tr>
<tr><td>

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook


<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook </b>
</tr>

<tr>
<td><font size="-1">Manuelles Anwenden, Ändern oder Entfernen einer Bezeichnung<td><font size="-1"><b>Ja</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Ja</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Ja</b><br><font size="-1">2.21+</font>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1"><b>Ja</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Bald verfügbar<sup>3</sup><td><font size="-1">Bald verfügbar<sup>3</sup>


<tr>
<td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Standardbezeichnung anwenden</a>
<td><font size="-1"><b>Ja</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Ja</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Ja</b><br><font size="-1">2.21+</font>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1"><b>Ja</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Bald verfügbar<sup>3</sup>


<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Begründung für das Ändern einer Bezeichnung anfordern</a><sup>1</sup>
<td><font size="-1"><b>Ja</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Ja</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Ja</b><br><font size="-1">2.21+</font>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1"><b>Ja</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Bald verfügbar<sup>3</sup>


<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Hilfelinks zu einer benutzerdefinierten Hilfeseite bereitstellen</a>
<td><font size="-1"><b>Ja</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Ja</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Ja</b><br><font size="-1">2.21+</font>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1"><b>Ja</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Bald verfügbar<sup>3</sup>


<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Inhalt markieren</a>
<td><font size="-1"><b>Ja</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Ja</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Ja</b><br><font size="-1">2.21+</font>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1"><b>Ja</b><br><font size="-1">16.0.11231+</font
><td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Bald verfügbar<sup>3</sup>


<tr><td><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">Zuweisen vordefinierter Berechtigungen</a>
<td><font size="-1"><b>Ja</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Ja</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Ja</b><br><font size="-1">2.21+</font>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1"><b>Ja</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Bald verfügbar<sup>3</sup>


<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Benutzern die Zuweisung von Berechtigungen überlassen</a>
<td><font size="-1"><b>Ja</b><sup>2</sup><br><font size="-1">1910+</font>

<td><font size="-1"><b>Ja</b><sup>2</sup><br><font size="-1">16.21.0+</font>

<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Noch nicht festgelegt<td
><font size="-1">Bald verfügbar<sup>3</sup>
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Bald verfügbar<sup>3</sup>

<tr><td><font size="-1">Daten der <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">Bezeichnungsanalyse</a> an Administratoren senden
<td><font size="-1">Noch nicht festgelegt

<td><font size="-1">Noch nicht festgelegt

<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt

<tr><td><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden</a>
<td><font size="-1">Noch nicht festgelegt

<td><font size="-1">Noch nicht festgelegt

<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Vertraulichkeitsbezeichnung automatisch auf Inhalte anwenden</a>
<td><font size="-1">Noch nicht festgelegt

<td><font size="-1">Noch nicht festgelegt

<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
<td><font size="-1">Noch nicht festgelegt
</table>

<br><sup>1</sup>Wenn konfiguriert, werden die Benutzer aufgefordert, Herabstufungen von Bezeichnungen zu begründen. Allerdings werden die Begründungsdaten Administratoren noch nicht zur Verfügung gestellt. Sie werden verfügbar, wenn die Funktion "Daten der Bezeichnungsanalyse an Administratoren senden" unterstützt wird.
<br><sup>2</sup>"Benutzern die Zuweisung von Berechtigungen überlassen" ist derzeit nur in Outlook für Windows und Mac verfügbar. Verfügbarkeit für Word, Excel und PowerPoint ist noch nicht festgelegt.
<br><sup>3</sup>Voraussichtlich Q4 des Kalenderjahrs 2019.

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a>Wann werden Inhaltskennzeichen oder Verschlüsselung angewendet, nachdem der Inhalt eine Vertraulichkeitsbezeichnung erhalten hat?

| Anwendung | Inhaltskennzeichnung | Verschlüsselung
| --- | --- | --- |
| Word, Excel, PowerPoint auf allen Plattformen | Sofort | Sofort |
| Outlook für PC und Mac | Nachdem E-Mails von Exchange Online gesendet werden | Sofort |
| Outlook im Web, für iOS und Android | Nachdem E-Mails von Exchange Online gesendet werden | Nachdem E-Mails von Exchange Online gesendet werden |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a>Können Vertraulichkeitsbezeichnungen neben dem Azure Information Protection-Client in Office für Windows ausgeführt werden?

Nein. Vertraulichkeitsbezeichnungen werden deaktiviert, wenn der Azure Information Protection-Client in Office für Windows geladen wird.

Wenn Sie den Azure Information Protection-Client installiert haben, aber stattdessen Vertraulichkeitsbezeichnungen verwenden möchten, haben Sie folgende Möglichkeiten:

1. Konfigurieren Sie das Gruppenrichtlinieneinstellung  **Vertraulichkeitsfeature in Office verwenden, um Vertraulichkeitsbezeichnungen anzuwenden und anzuzeigen** das unter **Benutzerkonfiguration/Administrative Vorlagen/Microsoft Office 2016/Sicherheitseinstellungen** zu finden ist.

  >Hinweis: Diese Einstellung kann über herkömmliche Bereitstellungsmechanismen für Gruppenrichtlinien oder über den [Office-Cloudrichtliniendienst](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service) bereitgestellt werden. 
 
  Alternativ können Sie auch den Azure Information Protection-Client deinstallieren oder  [deaktivieren](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d). 

2. Starten Sie alle Office-Anwendungen neu.

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a>Werden Vertraulichkeitsbezeichnungen in Nicht-Abonnementversionen von Office wie Office 2016 oder Office 2019 unterstützt?

Nein. Vertraulichkeitsbezeichnungen werden nur im Office 365-Abonnement und nicht in Nicht-Abonnementversionen unterstützt. Allerdings kann der Azure Information Protection-Client mit einheitlichen Bezeichnungen in Nicht-Abonnementversionen von Office verwendet werden. 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a>Ich habe vor dem Einrichten von Vertraulichkeitsbezeichnungen Schutzvorlagen bereitgestellt. Wo sind diese nun?

Die von Administratoren definierten [Schutzvorlagen](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) werden in der Office-Benutzeroberfläche ausgeblendet, wenn Vertraulichkeitsbezeichnungen aktiviert sind, da sie bei Verwendung von Vertraulichkeitsbezeichnungen mit aktivierter Verschlüsselung überflüssig sind. 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a>Kann eine Datei oder eine E-Mail-Nachricht mehr als eine Klassifizierung aufweisen?

Nein. Benutzer können für jedes Dokument oder jede E-Mail jeweils nur eine Bezeichnung auswählen.

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a>Wenn eine E-Mail mit einer Bezeichnung versehen ist, erhalten Anlagen automatisch dieselbe Bezeichnung?

Nein. Wenn Sie eine Bezeichnung auf eine E-Mail-Nachricht mit Anlagen anwenden, erben diese Anlagen nicht dieselbe Bezeichnung. Die Anlagen bleiben entweder ohne Bezeichnung oder behalten die möglicherweise separat angewendete Bezeichnung bei. Wenn die Bezeichnung für die E-Mail-Adresse aber Schutz anwendet, wird dieser Schutz für Office-Anlagen übernommen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

[Häufig gestellte Fragen zur Klassifizierung und zu Bezeichnungen in Azure Information Protection](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[Anwenden von Vertraulichkeitsbezeichnungen auf Ihre Dokumente und E-Mails in Office](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
