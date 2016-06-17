---
# required metadata

title: Eszközök regisztrálása | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Eszközök regisztrálása felügyeletre a Microsoft Intune-ban
A Microsoft Intune mobileszköz-kezelési (MDM) funkciója a regisztráció segítségével vonja felügyelet alá az eszközöket, és teszi lehetővé az erőforrásokhoz való hozzáférést. Az eszközök regisztrálásának módja az eszköz típusától, a tulajdonostól, és a felügyeleti szinttől függ. A „saját eszközök használata” (BYOD) és a vállalati tulajdonban lévő eszközök (COD) használata esetén szükség van a regisztrálási folyamatra. A helyi vagy felhőalapú Exchange ActiveSync programot használó vállalatok számára egyszerűbb, regisztráció nélküli felügyelet is megvalósítható. Az Intune ügyfélszoftvere segítségével Windows-számítógépek is felügyelhetők.

###  Támogatott eszközplatformok

Az Intune a következő eszközplatformokat képes kezelni:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Eszközök regisztrálásának lehetővé tétele  
 A regisztráció segítségével a felhasználók saját eszközükön is hozzáférhetnek a vállalati erőforrásokhoz, a rendszergazdák pedig ellenőrizhetik, hogy ezek az eszközök megfelelnek-e a vállalati erőforrások védelmét szolgáló szabályzatok előírásainak. Ez a legjobb módszer arra, hogy az Intune segítségével lehetővé váljon a „saját eszközök használata”. A rendszergazdának engedélyeznie kell a regisztrációt az Intune konzolban. Ehhez esetenként megbízhatósági kapcsolatot kell létrehozni az eszközzel, és licencet kell rendelni a felhasználókhoz. Ezt követően megtörténik az eszköz regisztrálása, általában azzal, hogy a felhasználó megadja munkahelyi vagy iskolai hitelesítő adatait. Az eszköz lekéri a szabályzatot az Intune-ból, és ezzel hozzáféréshez jut az erőforrásokhoz.

[Felkészülés az eszközök Intune-beli regisztrálására](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Vállalati tulajdonú eszközök regisztrálása
A vállalati tulajdonú eszközök (COD) az Intune konzol segítségével kezelhetők. Az iOS-eszközök az Apple által biztosított megoldások segítségével közvetlenül is regisztrálhatók. A rendszergazdák vagy menedzserek bármilyen típusú eszközt regisztrálhatnak az eszközregisztráció-kezelő segítségével. Az IMEI-számmal rendelkező eszközöket azonosítani lehet, és meg lehet jelölni vállalati tulajdonúként, ami lehetőséget nyújt a vállalati tulajdonú eszközök kezelésére.

[Vállalati tulajdonú eszközök regisztrálása](manage-corporate-owned-devices.md)

## Mobileszköz-kezelés az Exchange ActiveSync és az Intune használatával
Azok a mobileszközök, amelyek nincsenek regisztrálva, de kapcsolódnak az Exchange ActiveSync (EAS) rendszerhez, EAS MDM-szabályzat segítségével kezelhetők az Intune-ban. Az Intune egy helyi vagy felhőalapú Exchange Connector összekötő segítségével kommunikál az EAS-szel.



[Mobileszköz-kezelés az Exchange ActiveSync és az Intune használatával](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Windows rendszerű számítógépek felügyelete az Intune-nal  
Az Intune Windowsra készült számítógépes ügyfélszoftvere segítségével Windows-számítógépeket is kezelhet a Microsoft Intune-ban. Az Intune ügyfél által felügyelt Windows-számítógépek:

 - Képesek szoftver- és hardverleltár jelentésére
 - Képesek asztali alkalmazások telepítésére (például .exe és .msi kiterjesztésű fájlok segítségével)
 - Tűzfalbeállítások

Az Intune ügyfélszoftverével felügyelt számítógépeken nem lehet szelektív törlést végezni, az ilyen gépek nem vonhatók ki, és az Intune számos felügyeleti funkciója (például a feltételes hozzáférés, a VPN- és Wi-Fi-beállítások meghatározása vagy a tanúsítványok és e-mail-konfigurációk telepítése) sem használható.

[Windows rendszerű számítógépek felügyelete az Intune-nal](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


