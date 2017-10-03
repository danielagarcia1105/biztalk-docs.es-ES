---
title: Mediante el Explorador de hechos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, Facts Explorer
- business rules, vocabularies
- business rules, schemas
- business rules, databases
- business rules, .NET classes
- Facts Explorer [Business Rule Composer]
ms.assetid: ee125eb1-d5b9-4121-8a25-fcb7a640570e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4c84b01625bb1566d02c1679bfadd0100b7b406
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-facts-explorer"></a>Mediante el Explorador de hechos
El Explorador de hechos contiene cuatro pestañas: **vocabularios**, **esquemas XML**, **bases de datos**, y **clases .NET**.  
  
## <a name="vocabularies-tab"></a>pestaña Vocabularios  
 Use la **vocabularios** pestaña en el Explorador de hechos para administrar definiciones y versiones de vocabulario.  
  
 Use el menú contextual para obtener acceso a las siguientes opciones.  
  
|Use|Para|  
|--------------|----------------|  
|**Agregar nuevo vocabulario**|Crear un vocabulario nuevo.|  
|**Agregar nueva versión**|Crear una versión nueva vacía del vocabulario seleccionado. Puede copiar definiciones de otras versiones y pegarlas en la versión nueva.|  
|**Pegar versión de vocabulario**|Pegar el contenido de una versión de vocabulario copiada con anterioridad como una nueva versión en el vocabulario seleccionado.|  
|**Eliminar**|Eliminar el vocabulario seleccionado y todas sus versiones.|  
|**Agregar nueva definición**|Iniciar el Asistente para definición de vocabulario para crear una nueva definición en la versión de vocabulario seleccionada.|  
|**Guardar**|Guardar los cambios realizados en la versión seleccionada y sus definiciones.|  
|**Publicar**|Publicar la versión de vocabulario seleccionada. Tenga en cuenta que no puede modificar directamente una versión publicada. Puede copiarla y pegarla en una versión nueva del vocabulario.|  
|**Volver a cargar**|Volver a cargar la versión de vocabulario seleccionada y sus definiciones, con la opción de descartar cualquier cambio actual realizado en la versión y restaurar los contenidos del almacén de reglas.|  
|**Modificar**|Iniciar el Asistente de definición de vocabulario para cambiar la definición seleccionada. Tenga en cuenta que no puede modificar una definición que forma parte de una versión de vocabulario publicada.|  
|**Ir al hecho de origen**|Ir al hecho de origen correspondiente en un ensamblado .NET, un esquema XML o una tabla de bases de datos para la definición seleccionada.|  
  
## <a name="xml-schemas-tab"></a>pestaña Esquemas XML  
 Examine los esquemas XSD para buscar las definiciones de atributos y elementos XML. Puede arrastrar elementos a versiones de vocabulario no publicadas el **vocabulario** pestaña para crear definiciones o puede arrastrar elementos al Editor de condiciones o al Editor de acciones para definir predicados, acciones y argumentos.  
  
|Use|Para|  
|--------------|----------------|  
|**Seleccione el nodo raíz**|Seleccionar un nodo raíz para cargarlo de un esquema XML que contenga varios nodos raíz.|  
  
## <a name="databases-tab"></a>pestaña Bases de datos  
 Examine los servidores de bases de datos para buscar definiciones de tablas y bases de datos. Puede arrastrar elementos a versiones de vocabulario no publicadas el **vocabulario** pestaña para crear definiciones o puede arrastrar elementos al Editor de condiciones o al Editor de acciones para definir predicados, acciones y argumentos.  
  
## <a name="net-classes-tab"></a>pestaña Clases .NET  
 Examine los ensamblados .NET para buscar definiciones de clases .NET públicas. Puede arrastrar elementos a versiones de vocabulario no publicadas el **vocabulario** pestaña para crear definiciones o puede arrastrar elementos al Editor de condiciones o al Editor de acciones para definir predicados, acciones y argumentos.  
  
|Use|Para|  
|--------------|----------------|  
|**Examinar**|Cargar un ensamblado .NET de la caché de ensamblados global.|  
|**Quitar**|Quitar un ensamblado .NET|