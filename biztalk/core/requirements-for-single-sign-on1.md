---
title: Requisitos para el inicio de sesión único | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1111377-2fe1-4d65-ac0d-c89d2f1740b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43e54da709384611bffd1e05da6a79decc778e57
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015627"
---
# <a name="requirements-for-single-sign-on"></a>Requisitos para el inicio de sesión único
Para usar el inicio de sesión único (SSO), debe tener el software siguiente instalado:  
  
-   Microsoft BizTalk Server
  
-   Visual Studio  
  
-   Inicio de sesión único (SSO) empresarial  
  
-   Un sistema de servidor compatible con SSO  
  
-   El host aislado debe configurarse como **autenticación de confianza**.  
  
## <a name="enable-sso"></a>Habilitar SSO  
  
1.  En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.  
  
2.  Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.  
  
 Para obtener información acerca de cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications4.md).  
  
> [!NOTE]
>  Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**. Las aplicaciones que usen esas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad del adaptador de BizTalk para JD Edwards EnterpriseOne](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)