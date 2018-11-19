---
title: Androidos munkahelyi profilos eszközök regisztrálása az Intune-ban
titlesuffix: Microsoft Intune
description: Útmutató androidos munkahelyi profilos eszközök Intune-ban történő regisztrálásához.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a38c5db1e608cb5d9a047dc72ee9109e840096e0
ms.sourcegitcommit: 4d5e811d451aeb6307e0f64818e182e471ae1ed4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2018
ms.locfileid: "51618990"
---
# <a name="set-up-enrollment-of-android-work-profile-devices"></a>Androidos munkahelyi profilos eszközök regisztrálásának beállítása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune-nal úgy telepítheti az alkalmazásokat és a beállításokat az androidos munkahelyi profilos eszközökre, hogy elkülöníti egymástól a munkához kapcsolódó és a személyes adatokat. A Vállalati Androidra vonatkozó részletekről az [A Vállalati Android követelményei](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) című weboldal nyújt tájékoztatást.

Az androidos munkahelyi profil felügyelete a következő lépésekben állítható be:

1. [Az Intune-bérlő csatlakoztatása a Vállalati Android-fiókjához](connect-intune-android-enterprise.md).
2. Androidos munkahelyi profil regisztrációs beállításainak megadása. Az androidos munkahelyi profilok [csak bizonyos Android-eszközökön támogatottak](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Az androidos munkahelyi profilokat támogató eszközök mindegyike támogatja a hagyományos Android-alapú felügyeletet is. Az Intune-ban megadhatja, hogy hogyan történjen az androidos munkahelyi profilokat támogató eszközök felügyelete a [regisztrációs korlátozásokból](enrollment-restrictions-set.md).
    - **Blokkolás (alapértelmezett)**: Minden Android-eszköz, az androidos munkahelyi profilokat támogatókat is beleértve, hagyományos Android-eszközként lesz regisztrálva.
    - **Engedélyezés**: Az androidos munkahelyi profilokat támogató eszközök mindegyike androidos munkahelyi profilos eszközként lesz regisztrálva. Az androidos munkahelyi profilokat nem támogató eszközök hagyományos Android-eszközként lesznek regisztrálva.
3. [A felhasználók tájékoztatása arról, hogy miképpen regisztrálhatják az eszközeiket](/intune-user-help/enroll-your-device-in-intune-android).


Az androidos munkahelyi profilokat támogató, de korábban normál Android-eszközként regisztrált eszközök regisztrációját törölni kell, majd újra kell regisztrálni őket.

Ha az [Eszközregisztráció-kezelővel](device-enrollment-manager-enroll.md) regisztrál androidos munkahelyi profilos eszközöket, akkor a fiókonként regisztrálható eszközök számának felső korlátja 10.

További információ: [Az Intune által a Google-nek küldött adatok](data-intune-sends-to-google.md).

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>A Céges portál alkalmazás jóváhagyása a felügyelt Google Play Áruházban

Annak érdekében, hogy a felhasználók mindig hozzáférjenek a Céges portál alkalmazás legfrissebb verziójához, jóvá kell hagynia a Céges portál alkalmazást a felügyelt Google Play Áruházban. A jóváhagyással biztosítja, hogy minden felhasználó megkapja az automatikus frissítéseket. Ha nem hagyja jóvá a Céges portál alkalmazást, előfordulhat, hogy az nem fogja megkapni a Microsoft által kiadott fontos hibajavításokat és új funkciókat, és így idővel elavulttá válik.

Kövesse az alábbi lépéseket az Intune Céges portál alkalmazás jóváhagyásához:

1.  Keresse meg a Céges portál alkalmazást a [felügyelt Google Play Áruházban](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Jelentkezzen be a felügyelt Google Play Áruházba ugyanazzal a Google-fiókkal, amelyet a Vállalati Android-kötés konfigurálásához használt.
3.  Kattintson a **Jóváhagyás** lehetőségre. Ekkor megnyílik egy párbeszédpanel.
4.  Tekintse át a párbeszédpanelen látható engedélyeket, majd kattintson a **Jóváhagyás** lehetőségre. Ezeknek az engedélyeknek a jóváhagyására azért van szükség, hogy a Céges portál alkalmazás kezelni tudja az eszközön lévő munkahelyi profilt.
5.  Válassza a **Jóváhagyás fenntartása, amikor az alkalmazás új engedélyeket kér** lehetőséget, majd kattintson a **Mentés** gombra.

## <a name="next-steps-for-android-work-profiles"></a>További lépések az androidos munkahelyi profilokkal
- [Androidos munkahelyi profilos alkalmazások telepítése](apps-add-android-for-work.md)
- [Androidos munkahelyi profil-konfigurációs szabályzatok hozzáadása](device-profiles.md)
