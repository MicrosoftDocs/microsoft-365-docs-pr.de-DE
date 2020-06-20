---
title: Nachrichtenverschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
ms.custom:
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie verschlüsselte e-Mail-Nachrichten zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen.
ms.openlocfilehash: 527d7519ff9f20b4d7cf5a02cec6b0704802f8dc
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818730"
---
# <a name="message-encryption"></a>Nachrichtenverschlüsselung

People often use email to exchange sensitive information, such as financial data, legal contracts, confidential product information, sales reports and projections, patient health information, or customer and employee information. As a result, mailboxes can become repositories for large amounts of potentially sensitive information and information leakage can become a serious threat to your organization.

Mit der Office 365-Nachrichtenverschlüsselung kann Ihre Organisation verschlüsselte E-Mail-Nachrichten von bzw. zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen. Die Office 365-Nachrichtenverschlüsselung funktioniert mit Outlook.com, Yahoo!, Gmail und anderen E-Mail-Diensten. Die E-Mail-Nachrichtenverschlüsselung sorgt dafür, dass nur vorgesehene Empfänger verschlüsselte Nachrichten ansehen können.

## <a name="how-office-365-message-encryption-works"></a>Funktionsweise von Office 365 Nachrichtenverschlüsselung

Der Rest dieses Artikels gilt für die neuen OM-Funktionen.

Office 365 Nachrichtenverschlüsselung ist ein Onlinedienst, der auf Microsoft Azure Rights Management (Azure RMS) basiert, das Teil von Azure Information Protection ist. Dies umfasst Verschlüsselungs-, Identitäts-und Autorisierungsrichtlinien, um Ihre e-Mails zu schützen. Sie können Nachrichten mithilfe von Vorlagen für die Rechteverwaltung, der [Option "nicht weiterleiten"](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)und der [Option "nur verschlüsseln](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)" verschlüsseln.

Benutzer können dann e-Mail-Nachrichten und eine Vielzahl von Anlagen mithilfe dieser Optionen verschlüsseln. Eine vollständige Liste der unterstützten Anlagentypen finden Sie unter ["Dateitypen, die von IRM-Richtlinien abgedeckt werden, wenn Sie an Nachrichten angefügt werden" in Einführung in IRM für e-Mail-Nachrichten](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM).

Als Administrator können Sie auch e-Mail-Flussregeln definieren, um diesen Schutz anzuwenden. Sie können beispielsweise eine Regel erstellen, die die Verschlüsselung aller an einen bestimmten Empfänger adressierten Nachrichten erfordert oder die bestimmte Wörter in der Betreffzeile enthält, und auch angeben, dass Empfänger den Inhalt der Nachricht nicht kopieren oder ausdrucken können.

Im Gegensatz zur vorherigen Version von OM bieten die neuen Funktionen eine einheitliche Absender Erfahrung, unabhängig davon, ob Sie e-Mails innerhalb Ihrer Organisation oder an Empfänger außerhalb von Microsoft 365 senden. Darüber hinaus müssen Empfänger, die eine geschützte e-Mail-Nachricht erhalten, die an ein Microsoft 365-Konto in Outlook 2016 oder Outlook im Internet gesendet wird, keine weiteren Aktionen zum Anzeigen der Nachricht durchführen. Es funktioniert nahtlos. Empfänger, die andere e-Mail-Clients und e-Mail-Dienstanbieter verwenden, haben ebenfalls eine verbesserte Erfahrung. Weitere Informationen finden Sie unter [erfahren Sie mehr über geschützte Nachrichten in Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) und [wie öffne ich eine geschützte Nachricht](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).

Eine detaillierte Liste der Unterschiede zwischen der vorherigen Version von OM und den neuen OM-Funktionen finden Sie unter [Compare Versionen of OM](ome-version-comparison.md).

Wenn ein Benutzer eine e-Mail-Nachricht sendet, die einer Verschlüsselungs-e-Mail-Fluss Regel entspricht, wird die Nachricht verschlüsselt, bevor Sie gesendet wird. Alle Microsoft 365-Endbenutzer, die Outlook-Clients zum Lesen von e-Mails verwenden, erhalten systemeigene, erstklassige leseerlebnisse für verschlüsselte und durch Rechte geschützte e-Mails, auch wenn Sie sich nicht in derselben Organisation wie der Absender befinden. Unterstützte Outlook-Clients umfassen Outlook-Desktop, Outlook-Mac, Outlook Mobile auf IOS und Android sowie Outlook im Internet (früher bekannt als Outlook Web App).

Empfänger von verschlüsselten Nachrichten, die verschlüsselte oder durch Rechte geschützte e-Mails erhalten, die an Ihre Outlook.com-, Gmail-und Yahoo-Konten gesendet werden, erhalten eine Wrapper-e-Mail, die Sie an das OM-Portal weiterleitet, wo Sie sich leicht mit einem Microsoft-Konto, Gmail oder Yahoo-Anmeldeinformationen

Endbenutzer, die verschlüsselte oder durch Rechte geschützte e-Mails auf anderen Clients als Outlook lesen, verwenden auch das OM-Portal, um verschlüsselte und durch Rechte geschützte Nachrichten anzuzeigen, die Sie empfangen.

Wenn der Absender der geschützten e-Mail sich in gcc High befindet und sich der Empfänger außerhalb von gcc High befindet, einschließlich kommerzieller Benutzer, Outlook.com-Benutzer und Benutzer anderer e-Mail-Anbieter wie Gmail, erhält der Empfänger eine Wrapper-e-Mail. Die Wrapper-e-Mail leitet den Empfänger an das OM-Portal, in dem der Empfänger die Nachricht lesen und beantworten kann. Wenn sich der Absender und der Empfänger in der gcc-Umgebung befinden, auch wenn Sie sich nicht in derselben Organisation befinden, erhalten Empfänger, die Outlook-Clients zum Lesen von e-Mails verwenden, Native, erstklassige leseerlebnisse für verschlüsselte und durch Rechte geschützte e-Mails. Weitere Informationen zu den unterschiedlichen Erfahrungen in gcc High finden Sie unter [Compare Versionen of OM](ome-version-comparison.md).

Weitere Informationen zu Größenbeschränkungen für Nachrichten und Anlagen, die Sie mit OM verschlüsseln können, finden Sie unter [Exchange Online Limits](https://technet.microsoft.com/library/exchange-online-limits.aspx).

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Funktionsweise von Office 365 erweiterter Nachrichtenverschlüsselung auf der OM-Seite

Office 365 erweiterte Nachrichtenverschlüsselung können Sie mehrere Branding-Vorlagen erstellen, damit Sie die Steuerung über Empfänger Nachrichten optimieren und benutzerdefinierte Branding-Erlebnisse zur Unterstützung einer vielfältigen Organisationsstruktur erstellen können.

Die erweiterte Nachrichtenverschlüsselung in Microsoft 365 hilft Ihnen, Compliance-Verpflichtungen zu erfüllen, die eine flexiblere Kontrolle über den Zugriff durch externe Empfänger auf verschlüsselte e-Mails erfordern. Mit erweiterter Nachrichtenverschlüsselung in Office 365 können Sie als Administrator vertrauliche und außerhalb der Organisation freigegebene e-Mails mit automatischen Richtlinien steuern, die vertrauliche Informationstypen (beispielsweise PII, Finanz-oder Integritäts-IDs) oder Stichwörter zur Verbesserung des Schutzes durch Ablauf des Zugriffs über ein sicheres Webportal auf verschlüsselte e-Mails ermitteln. Darüber hinaus können Sie als Administrator verschlüsselte e-Mails, auf die extern über ein Microsoft 365-Webportal zugegriffen wird, weiter steuern, indem Sie den Zugriff auf eine e-Mail jederzeit widerrufen.

Die Sperrung und der Ablauf von Nachrichten funktionieren nur für e-Mails, die Ihre Benutzer an Empfänger außerhalb Ihrer Organisation senden. Darüber hinaus müssen die Empfänger über das Webportal auf die e-Mail zugreifen. Um sicherzustellen, dass der Empfänger das Portal zum Empfangen von e-Mails verwendet, richten Sie eine benutzerdefinierte Branding-Vorlage ein, die den Wrapper anwendet. Anschließend wenden Sie die Branding-Vorlage in einer e-Mail-Fluss Regel an. Weitere Informationen zur erweiterten Nachrichtenverschlüsselung finden Sie unter [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).

## <a name="defining-rules-for-office-365-message-encryption"></a>Definieren von Regeln für die Office 365-Nachrichtenverschlüsselung

Eine Möglichkeit, die neuen Funktionen für Office 365 Nachrichtenverschlüsselung zu aktivieren, besteht darin, dass Exchange Online-und Exchange Online Schutz Administratoren e-Mail-Flussregeln definieren. Diese Regeln bestimmen, unter welchen Bedingungen e-Mail-Nachrichten verschlüsselt werden sollen. Wenn eine Verschlüsselungsaktion für eine Regel festgelegt ist, werden alle Nachrichten, die mit den Regelbedingungen übereinstimmen, verschlüsselt, bevor Sie gesendet werden.

Nachrichtenfluss Regeln sind flexibel, sodass Sie Bedingungen kombinieren können, um bestimmte Sicherheitsanforderungen in einer einzigen Regel zu erfüllen. Sie können beispielsweise eine Regel zum Verschlüsseln aller Nachrichten definieren, die bestimmte Schlüsselwörter enthalten und an externe Empfänger adressiert sind. Die neuen Funktionen für Office 365 Nachrichtenverschlüsselung verschlüsseln auch Antworten von Empfängern verschlüsselter e-Mails.

Weitere Informationen zum Erstellen von Nachrichtenfluss Regeln, um die neuen OM-Funktionen nutzen zu können, finden Sie unter [define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-the-new-ome-capabilities"></a>Erste Schritte mit den neuen OM-Funktionen

Wenn Sie bereit sind, mit den neuen OM-Funktionen in Ihrer Organisation zu beginnen, finden Sie weitere Informationen unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md).

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Senden, Anzeigen und Beantworten von verschlüsselten E-Mail-Nachrichten

Mit Office 365 Nachrichtenverschlüsselung können Benutzer verschlüsselte e-Mails aus Outlook und Outlook im Internet senden. Darüber hinaus können Administratoren e-Mail-Flussregeln in Microsoft 365 einrichten, um e-Mails automatisch basierend auf Keyword-Übereinstimmungen oder anderen Bedingungen zu verschlüsseln.

Empfänger von verschlüsselten Nachrichten in Organisationen können diese Nachrichten nahtlos in einer Version von Outlook lesen, einschließlich Outlook für PC, Outlook für Mac, Outlook im Web, Outlook für IOS und Outlook für Android. Benutzer, die verschlüsselte Nachrichten auf anderen e-Mail-Clients empfangen, können die Nachrichten im OM-Portal anzeigen.

Ausführliche Anleitungen zum Senden und Anzeigen von verschlüsselten Nachrichten finden Sie in den folgenden Artikeln:

|||
|:-----|:-----|
|Lesen Sie diesen Artikel...|Wenn Sie...|
|[Informationen zu geschützten Nachrichten in Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|Endbenutzer, die mehr darüber erfahren möchten, wie verschlüsselte Nachrichten funktionieren und welche Optionen Ihnen zur Verfügung stehen.|
|[Wie öffne ich eine geschützte Nachricht?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|Ein Endbenutzer, der eine geschützte Nachricht lesen möchte, die Ihnen gesendet wurde. Dieser Artikel enthält Informationen zum Lesen von Nachrichten in mehreren Versionen von Outlook und aus unterschiedlichen e-Mail-Konten, einschließlich dieser Konten außerhalb von Microsoft 365 wie Gmail und Yahoo!. Konten.|
|[Senden, anzeigen und beantworten von verschlüsselten Nachrichten in Outlook](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|Ein Endbenutzer, der eine verschlüsselte Nachricht aus Outlook senden, anzeigen oder beantworten möchte. Selbst wenn Sie kein Mitglied einer Organisation sind, erhalten Sie weiterhin Benachrichtigungen über verschlüsselte Nachrichten, die Ihnen in Outlook gesendet werden. In diesem Artikel erhalten Sie Anleitungen zum Anzeigen und beantworten von verschlüsselten Nachrichten, die von Office 365 gesendet werden.|
|[Senden einer digital signierten oder verschlüsselten Nachricht](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Ein Endbenutzer, der verschlüsselte Nachrichten mit Outlook für Mac senden, anzeigen oder beantworten möchte. In diesem Artikel wird auch die Verwendung von anderen Verschlüsselungsmethoden als OM wie S/MIME behandelt.|
|[Anzeigen von verschlüsselten Nachrichten auf Ihrem Android-Gerät](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Ein Endbenutzer, der eine mit Office 365 Nachrichtenverschlüsselung auf Ihrem Android-Gerät verschlüsselte Nachricht erhalten hat, können Sie die ﻿kostenlose OM Viewer-App verwenden, um die Nachricht anzuzeigen und eine verschlüsselte Antwort zu senden. In diesem Artikel wird erläutert, wie.|
|[Verschlüsselte Nachrichten auf Ihrem iPhone oder iPad anzeigen](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|Ein Endbenutzer, der eine mit Office 365 Nachrichtenverschlüsselung auf Ihrem iPhone oder iPad verschlüsselte Nachricht erhalten hat, können Sie die ﻿kostenlose OM Viewer-App verwenden, um die Nachricht anzuzeigen und eine verschlüsselte Antwort zu senden. In diesem Artikel wird erläutert, wie.|
||
