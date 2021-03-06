---
title: Cómo configurar las propiedades de canalización por instancia para un puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- managing [pipelines], properties
- configuring, send ports
- configuring, pipelines
- managing [pipelines], configuring
- managing [send ports], pipelines
- managing [send ports], configuring
- send ports, pipelines
- pipelines, configuring
ms.assetid: c58faa9e-0dfb-458b-8f1b-d3c91bce0436
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d1d49f0c6f54341c14cb14c38cc0de7fefaa9a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991005"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-send-port"></a>Cómo configurar propiedades de canalización por instancia para un puerto de envío
Este tema describe cómo utilizar la consola de administración de BizTalk Server para configurar propiedades de canalización para un puerto de envío después de que la canalización se haya implementado en un grupo de BizTalk. Los cambios que se efectúen sobrescriben las propiedades de canalización predeterminadas únicamente de este puerto de envío, de modo que, si lo desea, podrá configurar propiedades de canalizaciones distintas para cada uno de los puertos de envío del grupo de BizTalk.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
> [!NOTE]
>  Al usar propiedades de canalización por instancia para establecer el valor de la **DocumentSpecNames** propiedad en el componente de desensamblador XML de una canalización, el esquema del documento especificado y la canalización debe definirse en el mismo proyecto.  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-send-port"></a>Para configurar propiedades de canalización por instancia para un puerto de envío  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene el puerto de envío para el que desea configurar las propiedades de canalización, expanda **aplicaciones**y, a continuación, Expanda la aplicación que contiene el puerto de envío.  
  
3. Haga clic en el **puertos de envío** carpeta, haga clic en el puerto de envío y, a continuación, haga clic en **propiedades**.  
  
4. Haga clic en el botón de puntos suspensivos (**...** ) situado a la derecha de la **canalización de envío** cuadro.  
  
5. Configure las propiedades que desee y, a continuación, haga clic en **Aceptar**. Haga clic en **ayuda** en la página de propiedades para obtener más información.  
  
   > [!IMPORTANT]
   >  Asegúrese de especificar información correcta para las propiedades de las canalizaciones. Si escribe un valor no válido (una cadena en lugar de un número, por ejemplo), se producirá un error.  
  
6. Si se trata de un puerto de envío de petición-respuesta, haga clic en el botón de puntos suspensivos (**...** ) situado a la derecha de la **canalización de recepción** cuadro.  
  
7. Configure las propiedades que desee y, a continuación, haga clic en **Aceptar** dos veces. Haga clic en **ayuda** en la página de propiedades para obtener más información.  
  
## <a name="see-also"></a>Vea también  
 [Administración de canalizaciones](../core/managing-pipelines.md)   
 [Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md)   
 [Administración de ubicaciones de recepción](../core/managing-receive-locations.md)