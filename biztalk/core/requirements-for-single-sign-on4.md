---
title: "Requisitos para el inicio de sesión único-EL4 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Single Sign-On, requirements
- SSO, enabling
- Single Sign-On, enabling
- SSO requirements
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15d7bdbf52869e5b13ae113716689bbb5b7ffec3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a>Requisitos para el inicio de sesión único
El Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) proporciona compatibilidad con inicio de sesión único (SSO). Una aplicación afiliada, creada por herramientas de Inicio de sesión único de la empresa, representa un sistema de servidor como TBCO EMS.  
  
 Para usar el inicio de sesión único (SSO), debe tener:  
  
-   Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   Inicio de sesión único (SSO) empresarial  
  
-   Un sistema de servidor que admite el SSO  
  
 El host aislado debe estar configurado como con autenticación de confianza.  
  
### <a name="to-enable-sso"></a>Para habilitar SSO  
  
1.  En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.  
  
2.  Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.  
  
     Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications5.md).  
  
    > [!NOTE]
    >  Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**. Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.  
  
## <a name="see-also"></a>Vea también  
 [Mediante el inicio de sesión único](../core/using-single-sign-on4.md)