---
title: Administrar ensamblados de BizTalk | Microsoft Docs
description: Vínculos a trabajar con ensamblados de BizTalk Server, incluido agregar, actualizar, ver las dependencias y quitar ensamblados
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62cc92f5-a1ea-46e4-88e6-b8a71a0c40a2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97dd8462aa0656334707d3eea55128b6e1702806
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001789"
---
# <a name="manage-biztalk-assemblies"></a>Administrar ensamblados de BizTalk

## <a name="overview"></a>Información general
En esta sección se proporcionan instrucciones sobre cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o la herramienta de la línea de comandos BTSTask para administrar ensamblados de BizTalk una vez que se han implementado en un grupo de BizTalk. Un ensamblado de BizTalk es un archivo DLL de Microsoft Windows que contiene información de recursos, como orquestaciones, canalizaciones, esquemas y asignaciones que se usarán en una solución empresarial de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener información general sobre los ensamblados de BizTalk, consulte [ensamblados de BizTalk](../core/biztalk-assemblies.md).  
  
> [!IMPORTANT]
>  Al implementar o anular la implementación de un esquema de propiedades, se pueden exponer datos confidenciales y, por lo tanto, información confidencial durante el seguimiento. Siempre que se implemente o se anule la implementación de un ensamblado que contenga un esquema de propiedades, el visor de eventos registrará un evento en el registro de eventos de aplicación de Windows. Debería comprobar el registro de eventos de estos mensajes para asegurarse de que todas las actividades de implementación de ensamblados están en línea con las directivas de datos confidenciales. (El mensaje generado en el registro de eventos para la implementación es: "El usuario"{1}"ha implementado el ensamblado"{0}"que contiene esquemas de propiedad". El mensaje generado en el registro de eventos para la anulación de implementación es: "El usuario"{1}"anulado la implementación del ensamblado"{0}"que contiene esquemas de propiedad".)  
> 
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas. Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
 El programador usa [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para desarrollar ensamblados de BizTalk, como se describe en [desarrollar aplicaciones de BizTalk Server](../core/developing-biztalk-server-applications.md)y puede implementarlos desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como se describe en [Deploying Ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md). El desarrollador también puede administrar ensamblados de BizTalk durante el proceso de desarrollo utilizando la consola de administración, como se describe en esta sección.  
  
## <a name="next-steps"></a>Pasos siguientes 
  
-   [Agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [Modificar las opciones de implementación de un ensamblado de BizTalk](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)  
  
-   [Ver las dependencias de un ensamblado de BizTalk](../core/how-to-view-the-dependencies-for-a-biztalk-assembly.md)  
  
-   [Quitar un ensamblado de BizTalk de una aplicación](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)