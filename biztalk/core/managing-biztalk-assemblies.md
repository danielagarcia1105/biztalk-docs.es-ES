---
title: Administrar ensamblados de BizTalk | Documentos de Microsoft
description: "Vínculos a trabajar con ensamblados de BizTalk Server, incluido agregar, actualizar, ver las dependencias y quitar ensamblados"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62cc92f5-a1ea-46e4-88e6-b8a71a0c40a2
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c0dc8e74e23c7dc0b3a4e7a62a76297988b6b2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="manage-biztalk-assemblies"></a>Administrar ensamblados de BizTalk

## <a name="overview"></a>Información general
En esta sección se proporcionan instrucciones sobre cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o la herramienta de la línea de comandos BTSTask para administrar ensamblados de BizTalk una vez que se han implementado en un grupo de BizTalk. Un ensamblado de BizTalk es un archivo DLL de Microsoft Windows que contiene información de recursos, como orquestaciones, canalizaciones, esquemas y asignaciones que se usarán en una solución empresarial de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener información general sobre los ensamblados de BizTalk, consulte [ensamblados de BizTalk](../core/biztalk-assemblies.md).  
  
> [!IMPORTANT]
>  Al implementar o anular la implementación de un esquema de propiedades, se pueden exponer datos confidenciales y, por lo tanto, información confidencial durante el seguimiento. Siempre que se implemente o se anule la implementación de un ensamblado que contenga un esquema de propiedades, el visor de eventos registrará un evento en el registro de eventos de aplicación de Windows. Debería comprobar el registro de eventos de estos mensajes para asegurarse de que todas las actividades de implementación de ensamblados están en línea con las directivas de datos confidenciales. (El mensaje generado en el registro de eventos para la implementación es: "el usuario"{{1}"implementado el ensamblado"{0}"que contiene esquemas de propiedad". El mensaje generado en el registro de eventos para la anulación es: "el usuario"{{1}"anularse el ensamblado que contiene esquemas de propiedad" {0}".")  
  
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
 El programador usa [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para desarrollar ensamblados de BizTalk, tal y como se describe en [desarrollar aplicaciones de BizTalk Server](../core/developing-biztalk-server-applications.md)y puede implementarlos desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tal y como se describe en [implementación Ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md). El desarrollador también puede administrar ensamblados de BizTalk durante el proceso de desarrollo utilizando la consola de administración, como se describe en esta sección.  
  
## <a name="next-steps"></a>Pasos siguientes 
  
-   [Agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [Modificar las opciones de implementación de un ensamblado de BizTalk](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)  
  
-   [Ver las dependencias de un ensamblado de BizTalk](../core/how-to-view-the-dependencies-for-a-biztalk-assembly.md)  
  
-   [Quitar un ensamblado de BizTalk desde una aplicación](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)