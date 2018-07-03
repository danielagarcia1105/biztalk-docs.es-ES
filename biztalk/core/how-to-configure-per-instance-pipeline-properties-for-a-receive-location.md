---
title: Cómo configurar las propiedades de canalización por instancia para una ubicación de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- receive locations, configuring
- managing [pipelines], properties
- managing [pipelines], receive locations
- managing [receive locations], pipelines
- managing [pipelines], configuring
- pipelines, receive locations
- pipelines, configuring
- receive locations, pipelines
- managing [receive locations], configuring
ms.assetid: e1ed3b10-2f39-479b-a3e6-22b4b2872192
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27c591e7ea30dd97b116f89c3d50d03ea48392b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982421"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-receive-location"></a>Cómo configurar propiedades de canalización por instancia para una ubicación de recepción
Este tema describe cómo utilizar la consola de administración de BizTalk Server para configurar propiedades de canalización para una ubicación de recepción después de que la canalización se haya implementado en un grupo de BizTalk. Los cambios que se efectúen solo sobrescriben las propiedades de canalización predeterminadas de esa ubicación de recepción, de modo que, si lo desea, podrá configurar propiedades de canalizaciones distintas para cada una de las ubicaciones de recepción del grupo de BizTalk.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
> [!NOTE]
>  Al usar propiedades de canalización por instancia para establecer el valor de la **DocumentSpecNames** propiedad en el componente de desensamblador XML de una canalización, el esquema del documento especificado y la canalización debe definirse en el mismo proyecto.  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-receive-location"></a>Para configurar propiedades de canalización por instancia para una ubicación de recepción  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene la ubicación de recepción para que se va a configurar las propiedades de canalización, expanda **aplicaciones**y, a continuación, Expanda la aplicación que contiene la ubicación de recepción.  
  
3. Haga clic en el **ubicaciones de recepción** carpeta, haga clic en la ubicación de recepción y, a continuación, haga clic en **propiedades**.  
  
4. Haga clic en el botón de puntos suspensivos (...) a la derecha de la **canalización de recepción** cuadro.  
  
5. Configure las propiedades que desee y, a continuación, haga clic en **Aceptar**. Para obtener más información, haga clic en **ayuda** en la página de propiedades.  
  
   > [!IMPORTANT]
   >  Asegúrese de especificar información correcta para las propiedades de las canalizaciones. Si escribe un valor no válido (una cadena en lugar de un número, por ejemplo), se producirá un error.  
  
6. Si se trata de una respuesta de solicitud de ubicación de recepción, haga clic en el botón de puntos suspensivos (...) a la derecha de la **canalización de envío** cuadro.  
  
7. Configure las propiedades que desee y, a continuación, haga clic en **Aceptar** dos veces. Para obtener más información, haga clic en **ayuda** en la página de propiedades.  
  
## <a name="see-also"></a>Vea también  
 [Administración de canalizaciones](../core/managing-pipelines.md)   
 [Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md)   
 [Administración de ubicaciones de recepción](../core/managing-receive-locations.md)