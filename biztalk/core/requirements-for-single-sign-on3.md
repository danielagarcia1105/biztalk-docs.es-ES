---
title: Requisitos de inicio de sesión único para el adaptador TIBCO Rendevous | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e61b456def74ee76d887fa42149ee95b9ca3cbf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013741"
---
# <a name="requirements-for-single-sign-on"></a>Requisitos para el inicio de sesión único

## <a name="prerequisites"></a>Requisitos previos
Para usar el inicio de sesión único (SSO), debe tener lo siguiente:  
  
-   Microsoft BizTalk Server
  
-   Visual Studio  
  
-   Inicio de sesión único (SSO) empresarial  
  
-   Un sistema de servidor que admita el inicio de sesión único  
  
-   El host aislado debe configurarse como autenticación de confianza.  
  
## <a name="enable-sso"></a>Habilitar el inicio de sesión único  
  
1. En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.  
  
2. Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.  
  
   Para obtener más información, consulte [crear aplicaciones afiliadas](../core/creating-affiliate-applications1.md).  
  
> [!NOTE]
>  Después de trabajar mediante SSO, no olvide restablecer cualquier carpeta de uso compartido de Web **no comparten**. Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.  
  
## <a name="see-also"></a>Vea también  
[Seguridad](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)