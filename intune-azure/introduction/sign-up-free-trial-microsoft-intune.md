---
title: "Regisztrálás a 30 napos ingyenes próbaverzióhoz"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Regisztráció az Intune-ra az Azure-on."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 01/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 29b33341b136c8e8d76b666f94a9f620212944c5
ms.lasthandoff: 02/18/2017


---

# <a name="sign-up-for-a-microsoft-intune-free-trial-for-the-azure-portal-preview"></a>Regisztráció a Microsoft Intune ingyenes, az Azure Portal előzetes verziójában elérhető próbaverziójára

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ez a cikk végigvezeti Önt az Azure Portal előzetes verziójához tartozó önálló Intune-próbaverzióra történő regisztráció lépésein. <!---and prepares your trial with some users so that you can then follow the associated evaluation guide to see how Intune manages mobile devices. ---> <!---or app data when devices are not enrolled in Intune.--->

<!--- ## Assumptions
This sign-up article and the evaluation guide assume you are using the trial for evaluation purposes only and intend to start with a clean environment when you subscribe.

To make it easy for you to get started with the trial, we are setting up a very simple environment that uses only Intune and assumes it will be your sole method of managing devices (known as the mobile device management authority). However, throughout the guide we will point you to deeper technical content if you want to explore farther.

You can do everything in the trial version that you can do in a subscription version; the only difference is you are limited to 100 user accounts in the trial.--->

<!--- ## Sign up for your trial--->
1. Látogasson el az [Intune regisztrációs](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) oldalára, és töltse ki az űrlapot a próbaverzióra való regisztrációhoz.

 <!--- If you have a work or school account and want to use that for your Intune trial, follow [these sign-in instructions](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1) instead. However, this article assumes that you are not using such an account.---><br/> ![A regisztrációs oldal képernyőképe](./media/1-clicking-try.png)

 > [!TIP]
> Ha az informatikai operatív tevékenység és a felhasználók túlnyomó része nem az Ön földrajzi helyén van, érdemes lehet azt az adott földrajzi helyet kiválasztania a **Hol működik a cége?** legördülő listában.

2. A regisztrációs folyamat végén egy üzenet jelenik meg, amely az új fiók adatait tartalmazza. <br/> ![Fiókadatok képernyőképe](./media/2-end-of-sign-up-process.png) <br/>Ha ekkor a **Minden készen áll** gombra kattint, megnyílik az Office 365 felügyeleti központja, ahol felhasználókat adhat a tesztkörnyezetéhez. <br/><br/>Ha viszont közvetlenül az Intune Azure Portal előzetes verziójába szeretne belépni, nyisson meg egy új böngészőablakot, és írja be a **https://portal.azure.com** címet a böngésző címsorába. Megnyílik az Azure bejelentkezési oldala, ahol a bejelentkezéshez megadhatja a kapott hitelesítő adatokat. Ezt a címet bármikor használhatja, amikor az Intune próbaverziójába szeretne belépni. <br/> ![Az Azure Portal bejelentkezési oldalának képernyőképe](./media/azure-portal-signin.png)

Amikor először jelentkezik be az Azure-os Intune előzetes verziójába, akkor előfordulhat, hogy az Intune nem jelenik meg az Azure-irányítópulton. Az Intune szolgáltatás felvétele az Azure-irányítópultra:
1. Az irányítópult bal oldalán, az Azure-szolgáltatások listájában kattintson a **További szolgáltatások >** elemre, és a keresőmezőbe írja be az **Intune** kifejezést.
2. Válassza a listából az **Intune** elemet, és a csillagra kattintva vegye fel a szolgáltatáslistára.<br/> ![Kép: az Intune kiválasztása a szolgáltatáslistából](./media/azure-add-intune1.png)
3. Ezután a szolgáltatáslistában az **Intune** elemet kiválasztva megnyithatja az Intune-irányítópultot.

Amikor próbaverziót regisztrál, e-mailben elküldjük a fiókadatait is a regisztráció során megadott e-mail címre. Az e-mail megerősíti, hogy a próbaverzió aktív.


<!--- ## Add users
Before you leave the Office 365 Admin center for Intune, you need to add some users to your trial account.

In the Office 365 Admin center, you can add users individually or in bulk by uploading a .csv file. We will do both to set up your trial. However, in your production environment, you will probably want to take advantage of your Azure Active Directory user accounts, which you can learn more about in our [Getting Started guide](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) and in the [Next steps](#Next-steps) section of this article.

### Add an individual user
1. Choose either of the options to add a use to open a form that allows you to create a user. Only the items starred with an asterisk (\*) are required.
![Image of add user button options](./media/sign-up/add-user.png)


2.  When you add the user, the final step will be to send the user an email with their temporary Intune password. For the purposes of this evaluation, use your own work email address so you will receive the log-on information and see the email your users will get. You can then use these user identities to enroll test devices.<br/>

 ![Image of add user final step](./media/sign-up/new-user-2.png)

3. If you want to assign a user an admin role after you create it, you can edit the role in the Office 365 Admin center by selecting the user name from your list of users, and then choosing **Edit** in the Role line to see the list of user roles you can select from and assign to that user.

 ![Image of user  role options](./media/sign-up/change-user-role.png)

### Import multiple users
1. You will find the wizard for importing multiple users in the **More** list.

 ![Image of option to add multiple users](./media/sign-up/add-multiple-users.png)

2. To help you set up your .csv file correctly, you can download a template file to populate with your user data. Download the .csv file that contains headers and sample user information to see exactly the kind of data is needed for each field.

 ![Image of first step in bulk enrollment wizard](./media/sign-up/bulk-enroll-step-1.png)


3. After you’ve created and saved your .csv file, choose **Browse** to select the file. Verify, and choose **Next**. Your users will be uploaded and added to your list of active users.

> [!NOTE]
> Your users won't show up in Intune until they've enrolled a device to be managed.

Now it’s time to head over to Intune to start managing your users, their devices, and their apps.--->

## <a name="keeping-the-admin-experiences-straight"></a>Átlátható felügyelet
<!---### Classic Intune
There are two portals you will use for classic Intune:
- The Office 365 Admin center ([portal.office.com](https://portal.office.com))
- The Intune administration console ([manage.microsoft.com](https://manage.microsoft.com))

Normally, you’ll do your work in the Intune administration console, shown below. This is the site where you set up and manage your groups, policies, devices, and apps.

![Image of Intune administration console](./media/sign-up/intune-admin-console.png)

However, you will use the Office 365 Admin center, shown below, to add and manage your users and other aspects of your account, including billing and support.

![Image of Office 365 Admin center](./media/sign-up/office-admin-center.png)

You can navigate from the Office 365 Admin center to the Intune admin console. The admin centers are under the last item in the left navigation pane. Choose **Intune** to open the Intune admin console in a new tab.

![Image of link to Intune administration console](./media/sign-up/link-to-intune.png)

To get from Intune back to the Office 365 Admin center, choose the **Add Users** task on the Groups Overview page.

![Image of link back to Office 365  Admin center](./media/sign-up/task-add-users.png)--->

<!---### Intune Azure preview--->
Az Azure-beli Intune előzeteshez három portált fog használni:
- Az Intune-irányítópultját az Azure-on ([portal.azure.com](https://portal.azure.com)), ahol megismerheti [mire képes az Intune az Azure Portalon](what-is-microsoft-intune.md).
- Az Office 365 Felügyeleti központot ([portal.office.com](https://portal.office.com)), ahol a felhasználókat adhatja hozzá és kezelheti, ha nem az Azure Active Directory-t használja ezekre a feladatokra. Továbbá fiókjának számlázási- támogatási- és egyéb aspektusait is kezelheti itt.
- A klasszikus Intune felügyeleti konzolt ([manage.microsoft.com](https://manage.microsoft.com)), ahol megismerheti azokat a funkciókat is, amelyek még nem elérhetőek az Azure-on.

Többnyire az alább látható Intune-irányítópulton fog dolgozni. Ezen az oldalon állíthatja be és kezelheti a csoportjait, szabályzatait, eszközeit és alkalmazásait.

A klasszikus Intune felügyeleti portált az irányítópultról éri el, a **Klasszikus Intune-portál megnyitása** csempét választva.

Ha vissza szeretne térni az Azure-beli Intune előzeteséhez, nyissa meg a https://portal.azure.com webhelyet a böngészőben, és válassza újból az **Intune** elemet a szolgáltatáslistából.

 ![Az Intune-irányítópult képe](./media/intune-azure-dashboard.png)


Az Office 365 felügyeleti központban (amelyet alább láthat) hozzáadhatja és kezelheti a felhasználókat, illetve a fiók más aspektusait, ideértve a számlázást és a támogatást is.

![Az Office 365 felügyeleti központját bemutató kép](./media/office-admin-center.png)

Ha az Office 365 felügyeleti központból szeretné elérni az Intune irányítópultot, nyissa meg a https://portal.azure.com webhelyet a böngészőben. Válassza a szolgáltatáslistából az **Intune** elemet.

Ha az Intune-ból szeretné elérni az Office 365 felügyeleti központot, nyissa meg a https://portal.office.com webhelyet a böngészőben. Ha már bejelentkezett az Intune-ba, akkor közvetlenül az Office 365 felügyeleti központba fog jutni.

## <a name="next-steps"></a>További lépések

### <a name="intune-azure-preview"></a>Intune az Azure-on – előzetes
További tudnivalók az [Azure-beli Intune előzetes verziójáról](what-is-microsoft-intune.md)
### <a name="classic-intune"></a>Klasszikus Intune
Kipróbálási forgatókönyv: [Mobileszköz-kezelés kipróbálása a Microsoft Intune-ban](https://docs.microsoft.com/intune/understand-explore/mobile-device-management-trial-guide-microsoft-intune)

### <a name="integration-with-other-products"></a>Integráció más termékekkel
Az Azure Active Directory felhasználói fiókok Intune-nal való használatával kapcsolatos további információk:
- [Identitáskövetelmények](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [A címtár-szinkronizálás követelményei](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Többtényezős hitelesítés követelményei](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

További információk [Az Intune és a System Center Configuration Manager együttes használatáról](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management)

