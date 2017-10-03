---
title: Administrar mapas | Documentos de Microsoft
description: "Vínculos para que funcionen con los mapas de BizTalk Server, como ver y quitar asignaciones"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e8e3057-5a9f-4b6b-b6ee-c71b7e6a51ac
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c86a1cd23fe8f06c2671be163409cd405e9cbe1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="manage-maps"></a>Administrar asignaciones

## <a name="overview"></a>Información general
En esta sección, se proporcionan instrucciones acerca de la administración de asignaciones desde la consola de administración de BizTalk Server. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa las asignaciones para traducir los registros y campos de un esquema a los de otro. Las asignaciones pueden usarse en orquestaciones, puertos de envío y puertos de recepción.  

## <a name="add-maps-to-an-application"></a>Agregar mapas a una aplicación  
 Se generan los mapas [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se compilan en ensamblados de BizTalk. No es posible agregar una asignación a una aplicación de manera individual; una asignación se agrega a una aplicación del modo que se especifica a continuación:  
  
-   Al agregar un ensamblado de BizTalk que contiene una asignación a la aplicación, como se describe en [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).  
  
-   Al importar un archivo .msi en una aplicación que incluye un ensamblado de BizTalk que contiene una asignación, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
-   Cuando un programador implementa en una aplicación un ensamblado que contiene una asignación de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], tal y como se describe en [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).  
  
 Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md). Para obtener información sobre la creación de mapas, vea [crear asigna utilizando el asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md).  
  
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="next-steps"></a>Pasos siguientes 
  
-   [Ver las asignaciones de una aplicación](../core/how-to-view-the-maps-for-an-application.md)  
  
-   [Quitar una asignación de una aplicación](../core/how-to-remove-a-map-from-an-application.md)