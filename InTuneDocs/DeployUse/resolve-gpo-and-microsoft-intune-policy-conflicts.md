---
# required metadata

title: GPO és Intune-szabályzatütközések feloldása| Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Csoportházirend-objektumok (GPO) és Microsoft Intune-szabályzatütközések feloldása
Az Intune szabályzatai megkönnyítik a beállítások kezelését az Ön által felügyelt számítógépeken. Használhat például egy olyan házirendet, amellyel Windows tűzfal beállításait szabályozhatja a számítógépeken. Az Intune számos beállítása hasonló a Windows csoportházirend-beállításaihoz. Néha előfordulhat azonban, hogy a két módszer ütközik egymással.

Ütközések esetén a tartományszintű csoportházirend elsőbbséget élvez az Intune szabályzatával szemben, kivéve, ha a számítógép nem tud bejelentkezni a tartományba. Ebben az esetben a rendszer az Intune szabályzatát alkalmazza az ügyfélszámítógépen.

## Mi a teendő a Csoportházirend használata esetén?
Ellenőrizze, hogy az Ön által alkalmazott szabályzatokat nem kezeli-e a csoportházirend. Az ütközések megelőzése érdekében fontolja meg az alábbi eljárások alkalmazását:

-   Helyezze át a számítógépeket egy olyan Active Directory-beli szervezeti egységbe (OU-ba), amelyre nem lettek alkalmazva csoportházirend-beállítások az Intune ügyfél telepítése előtt. Letilthatja továbbá a csoportházirend-öröklést azon OU-k esetében, amelyek olyan Intune-ban regisztrált számítógépeket tartalmaznak, amelyeken nem kívánja alkalmazni a csoportházirend-beállításokat.

-   WMI-szűrő vagy biztonsági szűrő használatával korlátozza a csoportházirend-objektumok alkalmazását az Intune által nem kezelt számítógépekre. Ehhez útmutatást és példákat a témakör [Meglévő csoportházirend-objektumok szűrése a Microsoft Intune szabályzatával való ütközések elkerülése érdekében](resolve-gpo-and-microsoft-intune-policy-conflicts.md#BKMK_Filter) című szakaszában talál.

-   Tiltsa le vagy távolítsa el az Intune szabályzataival ütköző csoportházirend-objektumokat.

Az Active Directoryról és a Windows csoportházirendjéről további információt a Windows Server dokumentációjában talál.

## Meglévő csoportházirend-objektumok szűrése az Intune szabályzatával való ütközések elkerülése érdekében
Ha azonosította azokat a csoportházirend-objektumokat (GPO-kat), amelyek beállításai ütköznek az Intune szabályzataival, az alábbi szűrési módszerek bármelyikével az Intune által nem kezelt számítógépekre korlátozhatja a GPO-k alkalmazását.

### WMI-szűrők használata
A WMI-szűrők szelektíven alkalmazzák a GPO-kat azokra a számítógépekre, amelyek megfelelnek a lekérdezés feltételeinek. A WMI-szűrők alkalmazásához telepítenie kell egy WMI-osztálypéldányt a vállalat összes számítógépén, mielőtt regisztrálná a számítógépeket az Intune szolgáltatásban.

#### WMI-szűrők alkalmazása GPO-ra

1.  Hozzon létre egy felügyeletiobjektum-fájlt az alábbi kód másolásával és szövegfájlba illesztésével, majd mentse a fájlt **WIT.mof** néven a kívánt helyre. A fájl azt a WMI-osztálypéldányt tartalmazza, amelyet az Intune szolgáltatásban regisztrálni kívánt számítógépeken telepíteni fog.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Telepítse a fájlt egy indítási parancsfájl vagy a csoportházirend használatával. Az indítási parancsfájlban az alábbi telepítési parancsot kell megadni. A WMI-osztálypéldányt az ügyfélszámítógépeknek az Intune szolgáltatásban való regisztrálása előtt kell telepíteni.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;MOF-fájl elérési útja&gt;\wit.mof**

3.  A WMI-szűrők létrehozásához futtassa az alábbi parancsok egyikét, attól függően, hogy a szűrni kívánt GPO az Intune használatával kezelt számítógépekre vagy az Intune használatával nem kezelt számítógépekre vonatkozik-e.

    -   Azon GPO-k esetében, amelyek az Intune használatával nem kezelt számítógépekre vonatkoznak, az alábbi parancsokat használja:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   Azon GPO-k esetében, amelyek az Intune használatával kezelt számítógépekre vonatkoznak, az alábbi parancsokat használja:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  A GPO Csoportházirend kezelése konzolban történő szerkesztésével alkalmazza az előző lépésben létrehozott WMI-szűrőt.

    -   Azon GPO-k esetében, amelyeknek csak az Intune használatával kezelni kívánt számítógépekre kell vonatkozniuk, a **WindowsIntunePolicyEnabled=1** szűrőt alkalmazza..

    -   Azon GPO-k esetében, amelyeknek csak az Intune használatával kezelni nem kívánt számítógépekre kell vonatkozniuk, a **WindowsIntunePolicyEnabled=0** szűrőt alkalmazza..

A WMI-szűrők csoportházirendbeli alkalmazásáról további tudnivalókat a [biztonsági szűrést, a WMI-szűrést és a csoportházirendbeli elemszintű célcsoportkezelést](http://go.microsoft.com/fwlink/?LinkId=177883) ismertető blogbejegyzésben talál..

### Biztonságicsoport-szűrők használata
A csoportházirend lehetővé teszi, hogy a GPO-kat csak azokra a biztonsági csoportokra alkalmazza, amelyek egy adott GPO Csoportházirend kezelése konzoljának **Biztonsági szűrés** területén vannak megadva. Alapértelmezés szerint a GPO-k a **Hitelesített felhasználók** csoportra vonatkoznak..

-   Az **Active Directory – felhasználók és számítógépek** beépülő modulban hozzon létre egy új biztonsági csoportot, amely az Intune használatával kezelni nem kívánt számítógépeket és felhasználói fiókokat tartalmazza. A csoportnak adhatja például a **Nem Microsoft Intune-beli** nevet.

-   A Csoportházirend kezelése konzolban, a kiválasztott GPO **Delegálás** lapján, kattintson a jobb gombbal az új biztonsági csoportra, és delegálja a megfelelő **olvasási** és **csoportházirend-alkalmazási** engedélyeket a biztonsági csoport felhasználóinak és számítógépeinek. A**csoportházirend-alkalmazási** engedélyek a **Speciális** párbeszédpanelen érhetők el.)

-   Ezután alkalmazza az új biztonságicsoport-szűrőt a kiválasztott GPO-ra, és távolítsa el az alapértelmezett **Hitelesített felhasználók** szűrőt.

Az új biztonsági csoportot regisztrációként kell kezelni az Intune szolgáltatásmódosításaiban.

### További információ
[Windows rendszerű számítógépek felügyelete a Microsoft Intune-nal](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


