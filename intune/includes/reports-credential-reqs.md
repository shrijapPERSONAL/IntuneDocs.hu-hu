<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Az Azure AD-beli és az Intune-beli hitelesítő adatokra vonatkozó követelmények

A hitelesítés és az engedélyezés az Azure AD-beli hitelesítő adatokon és az Intune szerepköralapú hozzáférés-vezérlésén (RBAC) alapul. Alapértelmezés szerint a bérlő valamennyi globális rendszergazdája és Intune-beli szolgáltatás-rendszergazdája hozzáféréssel rendelkezik az adattárházhoz. Az Intune-szerepkörök használatával azáltal biztosíthat több felhasználónak is hozzáférést, hogy hozzáférést ad nekik a **Jelentéskészítési erőforráshoz**.

Az Intune-adattárházhoz való hozzáférésre (beleértve az API-t is) vonatkozó követelmények a következők:

  -  Az Intune-licencet hozzá kell rendelni a felhasználóhoz
  -  A felhasználónak a következők egyikének kell lennie:
      -  Azure AD-beli globális rendszergazda
      -  Intune-beli szolgáltatás-rendszergazda
      -  A **Jelentések** erőforráshoz szerepköralapú hozzáféréssel rendelkező felhasználó