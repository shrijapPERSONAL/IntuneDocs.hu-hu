## <a name="enable-windows-10-automatic-enrollment"></a>Windows 10-es eszközök automatikus regisztrációjának engedélyezése

Az automatikus regisztrációval a felhasználók úgy regisztrálhatják vállalati tulajdonú vagy személyes Windows 10 rendszerű számítógépeiket és Windows 10 Mobile-eszközeiket az Intune-ban, hogy megadnak egy munkahelyi vagy iskolai fiókot és elfogadják, hogy felügyelet alá kerülnek. Ilyen egyszerű az egész! A háttérben a felhasználó eszköze regisztrálja magát és csatlakozik az Azure Active Directory-hoz. A regisztrációt követően az eszközt az Intune felügyeli.

**Előfeltételek**
- Azure Active Directory Premium-előfizetés ([próba-előfizetés](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune-előfizetés


### <a name="configure-automatic-mdm-enrollment"></a>Az automatikus MDM-regisztráció konfigurálása

1. Jelentkezzen be az [Azure felügyeleti portálra](https://portal.azure.com) (https://manage.windowsazure.com), és válassza az **Azure Active Directory** lehetőséget.

  ![Az Azure Portal képernyőképe](../media/auto-enroll-azure-main.png)

2. Válassza a **Mobilitás (MDM és MAM)** elemet.

  ![Az Azure Portal képernyőképe](../media/auto-enroll-mdm.png)

3. Válassza a **Microsoft Intune** elemet.

  ![Az Azure Portal képernyőképe](../media/auto-enroll-intune.png)

4. Állítsa be, hogy mely felhasználók regisztrálódjanak automatikusan.

  ![Az Azure Portal képernyőképe](../media/auto-enroll-scope.png)

  A következő URL-címekhez használja az alapértelmezett értékeket:
  - **MDM-regisztráció**
  - **MDM-használati feltételek**
  - **MDM-megfelelőség**

5. Adja meg, hogy mely felhasználók eszközeit felügyelje a Microsoft Intune. E felhasználók Windows 10 rendszerű eszközeit a rendszer automatikusan belépteti a Microsoft Intune-felügyeletbe.

  - **Összes**
  - **CSOPORTOK**
  - **Nincsenek**

6. Válassza a **Mentés** lehetőséget.
