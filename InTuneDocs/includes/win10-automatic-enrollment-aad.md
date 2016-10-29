## Azure Active Directory-regisztráció

Az automatikus regisztrációval a felhasználók úgy regisztrálhatják vállalati tulajdonú vagy személyes Windows 10 rendszerű számítógépeiket és Windows 10 Mobile-eszközeiket az Intune-ban, hogy megadnak egy munkahelyi vagy iskolai fiókot és elfogadják, hogy felügyelet alá kerülnek. Ilyen egyszerű az egész! A háttérben a felhasználó eszköze regisztrálja magát és csatlakozik az Azure Active Directory-hoz. A regisztrációt követően az eszközt az Intune felügyeli.

**Előfeltételek**
- Azure Active Directory Premium-előfizetés ([próba-előfizetés](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune-előfizetés


### Az automatikus MDM-regisztráció konfigurálása

1. Az [Azure felügyeleti portálján](https://manage.windowsazure.com) (https://manage.windowsazure.com) nyissa meg az **Active Directory** csomópontot és válassza ki a saját címtárát.

2. Kattintson az **Alkalmazások** lapra; a **Microsoft Intune** megjelenik az alkalmazások listájában.

    ![Azure AD-alkalmazások a Microsoft Intune-nal](../media/aad-intune-app.png)

3. Kattintson a **Microsoft Intune** melletti nyílra, ezzel megnyitja azt a lapot, amelyen konfigurálhatja az Intune-t.

4. A Microsoft Intune-nal való automatikus MDM-regisztráció konfigurálásának megkezdéséhez kattintson a **Konfigurálás** elemre.

5. Adja meg az URL-címeket az Intune-hoz:

  - **MDM-regisztrációs URL-cím** – Használja az alapértelmezett értéket.
  - **MDM használati feltételeinek URL-címe** – Használja az alapértelmezett értéket. Ez az URL-cím az eszközök beléptetésekor megjeleníti a használati feltételeket a felhasználók számára.
  - **MDM-megfelelőségi URL-cím** – Használja az alapértelmezett értéket. Amennyiben egy eszköz nem megfelelő, ezen az URL-címen jelenik meg a **Hozzáférés megtagadva** üzenet. Az URL-cím egy olyan oldalra mutat, amely ismerteti a felhasználóval, hogy miért nem megfelelő az eszköz és mit tehet a megfelelőség helyreállítása érdekében.

6.  Adja meg, hogy mely felhasználók eszközeit felügyelje a Microsoft Intune. E felhasználók Windows 10 rendszerű eszközeit a rendszer automatikusan belépteti a Microsoft Intune-felügyeletbe.

  - **Összes**
  - **Csoportok**
  - **Nincsenek**

7. Válassza a **Mentés** elemet.


<!--HONumber=Oct16_HO2-->


