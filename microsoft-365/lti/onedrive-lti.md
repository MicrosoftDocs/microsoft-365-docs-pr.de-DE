---
title: Verwenden der Interoperabilität mit Microsoft OneDrive Learning Tools
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Erstellen und Bewerten von Aufgaben, Erstellen und Kuratieren von Kursinhalten und Zusammenarbeit an Dateien in Echtzeit mit der neuen Interoperabilitäts-App für Microsoft OneDrive Learning Tools.
ms.openlocfilehash: 985a316bac689b9bc6c53ab65782d548fcad0db8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257018"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="7d4a5-103">Integrieren Microsoft OneDrive LTI in Canvas</span><span class="sxs-lookup"><span data-stu-id="7d4a5-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="7d4a5-104">Die Integration Microsoft OneDrive LTI in Canvas ist ein zweistufiger Prozess.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="7d4a5-105">Der erste Schritt aktiviert Microsoft OneDrive in Canvas, und im zweiten Schritt wird die Microsoft OneDrive LTI in Canvas-Kursen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="7d4a5-106">Empfohlene Browsereinstellungen</span><span class="sxs-lookup"><span data-stu-id="7d4a5-106">Recommended browser settings</span></span>

- <span data-ttu-id="7d4a5-107">Cookies sollten für Microsoft OneDrive aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="7d4a5-108">Popups sollten nicht für Microsoft OneDrive blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="7d4a5-109">Cookies sind im Inkognito-Modus des Chrome-Browsers nicht standardmäßig aktiviert und müssen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="7d4a5-110">Microsoft OneDrive LTI funktioniert im privaten Modus in Microsoft Edge Browser.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="7d4a5-111">Stellen Sie sicher, dass Sie keine Cookies blockiert haben (die standardmäßig aktiviert sind).</span><span class="sxs-lookup"><span data-stu-id="7d4a5-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="7d4a5-112">Aktivieren Microsoft OneDrive LTI in Canvas</span><span class="sxs-lookup"><span data-stu-id="7d4a5-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d4a5-113">Die Person, die diese Integration durchführt, sollte ein Administrator von Canvas und ein Administrator des Microsoft 365 Mandanten sein.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="7d4a5-114">Melden Sie sich beim <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI-Registrierungsportal an.</a></span><span class="sxs-lookup"><span data-stu-id="7d4a5-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="7d4a5-115">Wählen Sie die Schaltfläche **"Administratorzustimmung"** aus, und akzeptieren Sie die Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-115">Select the **Admin Consent** button and accept the permissions.</span></span>
1. <span data-ttu-id="7d4a5-116">Wählen Sie die Schaltfläche **"Neuen LTI-Mandanten erstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-116">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="7d4a5-117">**Wählen** Sie auf der LTI-Registrierungsseite canvas in der Dropdownliste aus, und geben Sie die Basis-URL Ihrer Canvas-Instanz ein.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-117">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="7d4a5-118">Wenn Ihre Canvas-Instanz z. B. https://contoso.test.instructure.com ]( https://contoso.test.instructure.com) ist, sollte die vollständige URL eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-118">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Die LTI-Mandantenverwaltungsseite mit einem Dropdownfeld zum Auswählen der LTI-Verbraucherplattform und einem URL-Textfeld.":::

4. <span data-ttu-id="7d4a5-120">Kopieren Sie den JSON-Code, indem Sie die Schaltfläche **"Kopieren"** auswählen (ein Symbol auf der rechten Seite, das zwei Seiten übereinander zeigt).</span><span class="sxs-lookup"><span data-stu-id="7d4a5-120">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="7d4a5-121">Dies wird verwendet, um den Schlüssel in Canvas zu generieren.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-121">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Ein Bild mit der Schaltfläche zum Kopieren, die den angezeigten JSON-Text kopiert und für die Schlüsselgenerierung in Canvas verfügbar macht.":::

5. <span data-ttu-id="7d4a5-123">Melden Sie sich als Administrator bei Ihrer Canvas-Instanz an, und wählen Sie im Menü auf der linken Seite der Seite die Option **"Entwicklerschlüssel"** aus.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-123">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="7d4a5-124">Erstellen Sie in der Dropdownliste einen Entwicklerschlüssel, indem Sie **LTI Key** aus der Dropdownliste oben rechts auf der Seite auswählen.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-124">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Screenshot der linken Navigationsleiste mit ausgewählten Entwicklerschlüsseln und ausgewählter LTI-Tasteneingabe in einer Dropdownliste auf der rechten Seite.":::

6. <span data-ttu-id="7d4a5-126">Wählen Sie auf der Seite "Konfigurieren" im Dropdown **"Methode"** die Option "JSON als Methode **einfügen"** aus, und fügen Sie den JSON-Text, den Sie in Schritt 5 kopiert haben, in das angezeigte Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-126">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="7d4a5-127">Speichern Sie den Schlüssel, und er wird in Canvas im **Status "Aus"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-127">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="7d4a5-128">Aktivieren Sie den **Schlüssel,** und kopieren Sie den in der Spalte **"Details"** angegebenen Schlüssel, der im nächsten Schritt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-128">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="Die Canvas-Seite, auf der der Schlüssel in einem ausgeschalteten Zustand festgelegt ist. Sie muss aktiviert sein, und der Schlüssel muss aus der Detailspalte auf dieser Seite kopiert werden.":::

8. <span data-ttu-id="7d4a5-130">Kehren Sie zum Microsoft OneDrive LTI-Registrierungsportal zurück, und fügen Sie den Schlüssel in das **Canvas-Client-ID-Feld** ein.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-130">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="7d4a5-131">Wählen Sie **"Weiter"** aus, wenn Sie bereit sind.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-131">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="Die LTI-Mandantenregistrierungsseite, die den JSON-Text und das Textfeld anzeigt, in das der Schlüssel kopiert werden soll.":::

9. <span data-ttu-id="7d4a5-133">Überprüfen und speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-133">Review and save your changes.</span></span> <span data-ttu-id="7d4a5-134">Bei erfolgreicher Registrierung wird eine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-134">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="7d4a5-135">Ihre Registrierungsdetails können auch überprüft werden, indem Sie auf der Startseite die Schaltfläche **"LTI-Mandanten anzeigen"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-135">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="7d4a5-136">Aktivieren Microsoft OneDrive LTI in Canvas-Kursen</span><span class="sxs-lookup"><span data-stu-id="7d4a5-136">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="7d4a5-137">Ein Canvas-Administrator kann Microsoft OneDrive LTI für alle Kurse aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-137">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="7d4a5-138">Wenn Microsoft OneDrive LTI in einem bestimmten Kurs (und nicht in allen Kursen) benötigt wird, muss die Kursleiterin die gleichen Schritte in den Kurseinstellungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-138">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="7d4a5-139">Melden Sie sich als Administrator an, und wechseln Sie zum **Abschnitt Einstellungen.**</span><span class="sxs-lookup"><span data-stu-id="7d4a5-139">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="7d4a5-140">Wechseln Sie zum Abschnitt **"Apps",** und wählen Sie die Schaltfläche **"App-Konfigurationen anzeigen" aus.**</span><span class="sxs-lookup"><span data-stu-id="7d4a5-140">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="7d4a5-141">Wählen Sie die Schaltfläche **"App hinzufügen"** aus.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-141">Select the **Add App** button.</span></span>
4. <span data-ttu-id="7d4a5-142">Wählen Sie im Dropdownmenü **"Konfigurationstyp"** die Option **"Nach Client-ID"** aus.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-142">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="7d4a5-143">Fügen Sie den Wert des zuvor generierten Entwicklerschlüssels in das **Feld "Client-ID"** ein, und wählen Sie die Schaltfläche **"Absenden"** aus.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-143">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="Die Seite &quot;App hinzufügen&quot;, auf der die Option &quot;Nach Client-ID&quot; im Dropdownmenü &quot;Konfigurationstyp&quot; angezeigt wird.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="7d4a5-145">Zusammenarbeits-Einstellungen für Microsoft OneDrive LTI in Canvas-Kursen</span><span class="sxs-lookup"><span data-stu-id="7d4a5-145">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="7d4a5-146">Damit die Zusammenarbeit für Lehrkräfte und Schüler/Studenten funktioniert, sollten Sie die Einstellung für die Zusammenarbeit nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-146">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="7d4a5-147">Führen Sie die folgenden Schritte aus, um sicherzustellen, dass die Einstellung nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-147">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="7d4a5-148">Melden Sie sich als Administrator an, und wechseln Sie zum **Abschnitt Einstellungen.**</span><span class="sxs-lookup"><span data-stu-id="7d4a5-148">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="7d4a5-149">Wechseln Sie zum Abschnitt **"Featureoptionen",** und wechseln Sie dann zum Abschnitt **"Kurs".**</span><span class="sxs-lookup"><span data-stu-id="7d4a5-149">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="7d4a5-150">Legen Sie fest, dass das Feature **"Tool für externe Zusammenarbeiten"** nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-150">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="7d4a5-151">Die Zusammenarbeit kann einzelnen Kursteilnehmern und Gruppen von Kursteilnehmern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-151">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="7d4a5-152">Das Zuweisen zu einzelnen Kursteilnehmern funktioniert standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-152">Assigning to individual students works by default.</span></span> <span data-ttu-id="7d4a5-153">Führen Sie die folgenden Schritte aus, um einer Gruppe von Schülern/Studenten zusammenarbeiten zu können:</span><span class="sxs-lookup"><span data-stu-id="7d4a5-153">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="7d4a5-154">Melden Sie sich als Administrator an, und wechseln Sie zum Abschnitt **"Entwicklerschlüssel".**</span><span class="sxs-lookup"><span data-stu-id="7d4a5-154">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="7d4a5-155">Suchen Sie den Schlüssel mit dem Wert 170000000000710, und legen Sie ihn auf **"Ein"** fest.</span><span class="sxs-lookup"><span data-stu-id="7d4a5-155">Find the key with value 170000000000710 and set it to **On**.</span></span>
