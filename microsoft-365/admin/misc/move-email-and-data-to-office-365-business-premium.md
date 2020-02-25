---
title: Verschieben von E-Mails und Daten nach Office 365 Business Premium
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1062115d-e312-482a-bb5a-765235990f41
ROBOTS: NOINDEX
description: In diesem Artikel erfahren Sie, wie Sie Daten in Ihre neue Geschäftsidentität umlegen.
ms.openlocfilehash: 878d4b66907cc6419ff23cbb61e56e32c7c601bc
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254267"
---
# <a name="move-email-and-data-to-office-365-business-premium"></a>Verschieben von E-Mails und Daten nach Office 365 Business Premium

Wenn Sie ein Upgrade auf Office 365 Business Premium durchführen, erhalten Sie eine ganz neue *Geschäftsidentität*. Sie erhalten ein neues E-Mail-Konto und ein separates OneDrive-Konto für Ihre Geschäftsdaten. 
  
Wenn Sie einige Ihrer persönlichen Daten auf die neue Business-Identität verschieben möchten, folgen Sie den nachstehenden Anweisungen.
  
## <a name="onedrive"></a>[OneDrive](#tab/OneDrive)
  
 **Kopieren Ihrer OneDrive-Daten**
1. Erstellen Sie einen temporären Ordner auf Ihrer Festplatte, um die Dateien vorübergehend zu speichern, die Sie nach Office 365 Business migrieren möchten.
    
2. Wechseln Sie [https://onedrive.live.com/](https://onedrive.live.com/) zu, und melden Sie sich mit dem Microsoft-Konto an, das Sie für den Zugriff auf Ihr Office 365 für Privat Abonnement verwenden. 
    
3. Kopieren Sie die Dateien, die Sie in Office 365 Business verwenden möchten, in den in Schritt 1 erstellten lokalen Ordner.
    
 **IImportieren von OneDrive-Dateien nach Office 365 Business**
1. Wechseln Sie zu [Admin.Microsoft.com](https://go.microsoft.com/fwlink/?LinkId=816877) , und melden Sie sich mit Ihrem Office 365 Geschäftsbenutzer Namen und Kennwort an. 
    
2. Select the **app launcher** icon in the upper-left and then choose **OneDrive**.
  
    > [!TIP]
    > Beim ersten Öffnen von OneDrive for Business müssen Sie OneDrive einrichten. Wenn dies der Fall ist, wählen Sie auf der Seite **Willkommen bei OneDrive für Unternehmen** die Option **weiter**aus. Nachdem OneDrive eingerichtet wurde, wählen Sie **Ihr OneDrive ist Ready**aus. 
  
3. Nun wird ein leere OneDrive-Ordner angezeigt. Wenn Sie Unterordner erstellen möchten, wählen Sie **neuer** \> **Ordner**aus.

4. Wählen Sie **hochladen** aus, um die Dateien von Ihrer Festplatte zu kopieren, auf der Sie die OneDrive-Dateien kopiert haben. 
  
    > [!NOTE]
    >  Sie können einzelne Dateien und Dateigruppen (wie alle Dateien in einem bestimmten Ordner) gleichzeitig hochladen, Sie können jedoch keinen Ordner nach OneDrive for Business kopieren. Stattdessen müssen Sie in OneDrive for Business die gewünschte Ordnerstruktur erstellen. >  Wenn Sie Dateien in einen Ordner kopieren möchten, den Sie in Schritt 4 erstellt haben, öffnen Sie den Ordner, bevor Sie die Dateien hochladen. Andernfalls werden die Dateien in den Stammordner hochgeladen. Sie können die Dateien auch zwischen den Ordnern in OneDrive for Business verschieben, nachdem Sie sie hochgeladen haben. 
  
## <a name="outlookemail"></a>[Outlook/E-Mail](#tab/Outlook)
  
 **Exportieren von Outlook 2013-Daten in eine Outlook-Datendatei**
1. Bevor Sie eine Outlook-Datendatei (PST) erstellen können, muss das Konto, aus dem Sie Outlook-Daten exportieren möchten, bereits in der Desktopversion von Outlook hinzugefügt worden sein. Weitere Informationen zum Hinzufügen eines Kontos in Outlook 2013 oder höher finden Sie unter [Einrichten von E-Mail in Outlook (für Windows](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) oder [Einrichten von E-Mail in Outlook für Mac 2011](https://support.office.com/article/d7b404a0-6e18-4d95-bed8-2de7661563ca.aspx).
    
2. Jeden Benutzer muss die Schritte unter [Exportieren oder Sichern von E-Mails, Kontakten und Kalender in einer Outlook-PST-Datei](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) ausführen.
    
 **Einrichten Ihres neuen E-Mail-Kontos in Outlook**
1. Jeder Benutzer muss im Office 365 Business-Abonnement ein neues E-Mail-Konto einrichten. Hierfür benötigt er die Adresse des neuen E-Mail-Kontos. Der Name des E-Mail-Kontos des Benutzers ist derselbe wie der Benutzername, mit dem er sich bei Office 365 anmeldet. Also beispielsweise: laura@onmicrosoft.com oder karl@contoso.com.
    
2. Bitten Sie jeden Benutzer, sein E-Mail-Konto in Outlook hinzuzufügen. Wenn Sie wissen möchten, wie das geht, lesen Sie [Einrichten von E-Mail in Outlook (für Windows)](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) oder [Einrichten von E-Mail in Outlook für Mac 2011](https://support.office.com/article/d7b404a0-6e18-4d95-bed8-2de7661563ca.aspx).
    
 **Importieren von -Daten aus einer Outlook-Datendatei**
1. Damit werden die E-Mails, Kalender, Aufgaben und Kontakte, die sich in der PST-Datei befinden, im Office 365 Business-E-Mail-Konto zusammengeführt.
    
2. Zum Importieren der Daten aus der PST-Datei in sein Office 365 Business-E-Mail-Konto muss jeder Benutzer die Schritte in [Importieren von E-Mails, Kontakten und Kalendern aus einer Outlook-PST-Datei](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac.aspx) ausführen.
    
---

