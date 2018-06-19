---
title: Requisitos de SSO para el adaptador TIBCO EMS | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 805d14e056da665f8828ce0244f28ed9adc40ff4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24012979"
---
# <a name="requirements-for-single-sign-on"></a>Requisitos para el inicio de sesión único

## <a name="overview"></a>Información general
El Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) proporciona compatibilidad con inicio de sesión único (SSO). Una aplicación afiliada, creada por herramientas de Inicio de sesión único de la empresa, representa un sistema de servidor como TBCO EMS.  
  
 Para usar el inicio de sesión único (SSO), debe tener:  
  
-   Microsoft BizTalk Server
  
-   Visual Studio  
  
-   Inicio de sesión único (SSO) empresarial  
  
-   Un sistema de servidor que admite el SSO  
  
 El host aislado debe configurarse como autenticación de confianza.
  
## <a name="enable-sso"></a>Habilitar SSO  
  
1.  En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.  
  
2.  Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.  
  
     Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications5.md).  
  
    > [!NOTE]
    >  Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**. Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.  
  
## <a name="see-also"></a>Vea también  
[Proteger el adaptador](../core/security-in-biztalk-adapter-for-tibco-ems.md)