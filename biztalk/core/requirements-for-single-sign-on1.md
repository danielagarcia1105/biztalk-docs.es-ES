---
title: Requisitos para el inicio de sesión único | Microsoft Docs
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
ms.openlocfilehash: 9045c51470d666906c090b55d6307c9f85d20e0c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022482"
---
# <a name="requirements-for-single-sign-on"></a>Requisitos para el inicio de sesión único
Para usar el inicio de sesión único (SSO), debe tener el software siguiente instalado:  
  
-   Microsoft BizTalk Server
  
-   Visual Studio  
  
-   Inicio de sesión único (SSO) empresarial  
  
-   Un sistema de servidor compatible con SSO  
  
-   El host aislado debe configurarse como **autenticación de confianza**.  
  
## <a name="enable-sso"></a>Habilitar el inicio de sesión único  
  
1. En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.  
  
2. Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.  
  
   Para obtener información acerca de cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications4.md).  
  
> [!NOTE]
>  Después de trabajar mediante SSO, no olvide restablecer cualquier carpeta de uso compartido de Web **no comparten**. Las aplicaciones que usen esas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad del adaptador de BizTalk para JD Edwards EnterpriseOne](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)