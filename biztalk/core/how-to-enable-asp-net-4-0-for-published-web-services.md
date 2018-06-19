---
title: Cómo habilitar ASP.NET 4.0 para publican servicios Web | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58646ff2-77a3-49dc-8593-f6e41d85d4f3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e68b8eef114828ad181e83ce0c7acd70a5545e0d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254084"
---
# <a name="how-to-enable-aspnet-40-for-published-web-services"></a>Cómo habilitar ASP.NET 4.0 para servicios Web publicados
Establezca la versión de ASP.Net en IIS.

El Asistente de publicación de servicios de BizTalk Server Web se basa en la funcionalidad proporcionada con ASP.NET, que se incluye con .NET Framework. Las versiones de ASP.Net se incluyen con la versión de .NET CLR que elija. 

En este tema se muestra cómo cambiar la versión de CLR. NET. 

## <a name="prerequisites"></a>Requisitos previos

IIS se incluye con la **servidor Web (IIS)** rol en el sistema operativo. Al instalar este rol, seleccione también la versión más reciente de ASP.NET. 
  
## <a name="update-an-application-pool"></a>Actualizar un grupo de aplicaciones
  
1.  Abra **de Internet Information Services (IIS) Manager**:

    1. En **el administrador del servidor**, seleccione **herramientas**.
    2. Seleccione **de Internet Information Services (IIS) Manager**.
  
2.  Expanda el nombre del servidor y seleccione **grupos de aplicaciones**.  
  
3.  Seleccione el grupo de aplicaciones y abra el **configuración básica**.  
  
4. Establecer el **versión de .NET CLR** a la versión más reciente y seleccione **Aceptar** para guardar los cambios.  

> [!NOTE]
> También puede cambiar la versión en el archivo web.config.
 
## <a name="allow-the-aspnet-extension"></a>Permitir la extensión de ASP.Net
  
1.  Abra **de Internet Information Services (IIS) Manager**:

    1. En **el administrador del servidor**, seleccione **herramientas**.
    2. Seleccione **de Internet Information Services (IIS) Manager**.
  
2.  Seleccione el nombre del servidor y haga doble clic en **restricciones de ISAPI y CGI**.  
  
3. Confirmar ASP.NET es **permitido** para las versiones de 32 bits y 64 bits.  
  
## <a name="see-also"></a>Vea también  
 [Planificación para publicar servicios Web](../core/planning-for-publishing-web-services2.md)