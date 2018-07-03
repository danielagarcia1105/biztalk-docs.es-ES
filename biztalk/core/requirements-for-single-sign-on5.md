---
title: Requisitos para el inicio de sesión único | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 318b9977-ce24-48d6-971b-49a059a1bdbc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48346802c25e4b5aeb4d6ac1d5e83552b1220149
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005493"
---
# <a name="requirements-for-single-sign-on"></a>Requisitos para el inicio de sesión único
Para usar el inicio de sesión único (SSO), debe tener:  
  
- Microsoft BizTalk Server 
  
- Visual Studio  
  
- Inicio de sesión único (SSO) empresarial  
  
- Un sistema de servidor compatible con SSO  
  
  El host aislado debe configurarse como autenticación de confianza.  
  
## <a name="enable-sso"></a>Habilitar el inicio de sesión único  
  
1.  En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.  
  
2.  Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.  
  
     Para obtener información acerca de cómo crear aplicaciones afiliadas, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications3.md).  
  
    > [!NOTE]
    >  Después de trabajar mediante SSO, no olvide restablecer cualquiera **uso compartido de Web** carpeta **no comparten**. Las aplicaciones que usen esas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad en el adaptador](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)