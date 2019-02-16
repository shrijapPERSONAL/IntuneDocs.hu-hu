## <a name="enable-windows-10-automatic-enrollment"></a>Windows 10-es eszközök automatikus regisztrációjának engedélyezése

Az automatikus regisztrálással a felhasználók Windows 10-es eszközeiket regisztrálhatják az Intune-ban. A regisztráláshoz a felhasználónak a személyes tulajdonú eszközén hozzá kell adnia a munkahelyi fiókját, vagy a céges tulajdonban lévő eszközt csatlakoztatnia kell az Azure Active Directoryhoz. A háttérben az eszköz regisztrálja magát, és csatlakozik az Azure Active Directoryhoz. A regisztrációt követően az eszközt az Intune felügyeli.

**Előfeltételek**
- Azure Active Directory Premium-előfizetés ([próba-előfizetés](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune-előfizetés


### <a name="configure-automatic-mdm-enrollment"></a>Az automatikus MDM-regisztráció konfigurálása

1. Jelentkezzen be az [Azure Portalon](https://portal.azure.com), majd válassza az **Azure Active Directory** elemet.

   ![Az Azure Portal képernyőképe](../media/auto-enroll-azure-main.png)

2. Válassza a **Mobilitás (MDM és MAM)** elemet.

   ![Az Azure Portal képernyőképe](../media/auto-enroll-mdm.png)

3. Válassza a **Microsoft Intune** elemet.

   ![Az Azure Portal képernyőképe](../media/auto-enroll-intune.png)

4. Konfigurálja az **MDM-felhasználói hatókört**. Adja meg, hogy mely felhasználók eszközeit felügyelje a Microsoft Intune. Ezeket a Windows 10 rendszerű eszközöket a rendszer automatikusan regisztrálni tudja a Microsoft Intune-felügyeletbe.

   - **Nincs** – Automatikus MDM-regisztráció letiltva
   - **Néhány** – Kiválaszthatja a **csoportokat**, melyek automatikusan regisztrálhatják Windows 10-es eszközeiket
   - **Mind** – Minden felhasználó automatikusan regisztrálhatja Windows 10-es eszközeit

      > [!IMPORTANT]
      > A BYOD-eszközök esetén a MAM-felhasználói hatókör Ha MAM-felhasználói hatókör és az MDM-felhasználói hatókör (automatikus MDM-regisztráció) engedélyezve van az összes felhasználó (vagy a felhasználók ugyanazok a csoportok) élvez elsőbbséget. Az eszköz használandó Windows Information Protection (WIP) házirendek (Ha úgy állította be őket) ahelyett, hogy az MDM-regisztrálása folyamatban van.
      >
      > Vállalati eszközök esetén az MDM-felhasználói hatókör két hatókörnek engedélyezésével élvez elsőbbséget. Az eszközök MDM-regisztrálása beolvasása.

   > [!NOTE]
   > MAM-felhasználói hatókör állítson be egy felhasználói csoport vagy a gyűjtemény.

   ![Az Azure Portal képernyőképe](../media/auto-enroll-scope.png)

5. A következő URL-címekhez használja az alapértelmezett értékeket:
    - **MDM használati feltételeinek URL-címe**
    - **MDM-felderítési URL-cím**
    - **MDM megfelelőségi URL-címe**

6. Kattintson a **Mentés** gombra.

Alapértelmezés szerint a kétfaktoros hitelesítés nincs engedélyezve a szolgáltatáshoz. Ezzel együtt azonban az eszköz regisztrálásához ajánlatos kétfaktoros hitelesítést használni. A kétfaktoros hitelesítés engedélyezéséhez konfigurálnia kell egy kétfaktoros hitelesítési szolgáltatót az Azure AD-ban, a felhasználói fiókokat pedig többtényezős hitelesítéshez kell konfigurálnia. További információt az [Azure Multi-Factor Authentication-kiszolgáló – első lépések](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud) című témakörben talál.
