---
title: "Configuración de vínculos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10050c28-0944-4073-afd2-54cd6c8d79a2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3da50b626eeb65a137deb8a1a7ef4f2ee3e0609
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-links"></a>Configurar vínculos

## <a name="overview"></a>Información general
Los vínculos tienen propiedades que se muestran en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de propiedades cuando se selecciona un vínculo en la página de cuadrícula mostrada. Para obtener información de referencia acerca de las propiedades asociadas con los vínculos, consulte **propiedades de vínculo de** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. 

## <a name="source-target-and-label"></a>Origen, destino y etiqueta  
 Las siguientes propiedades configuran vínculos en una asignación:  
  
-   **Vínculos de origen**. Usa el **vínculos de origen** propiedad para configurar la naturaleza de los datos de un mensaje de instancia de entrada que se utilizará para construir el mensaje de instancia de salida. La opción predeterminada y más común es utilizar el valor de elemento o atributo del mensaje de instancia de entrada. Existen otras posibles opciones, incluida la utilización del nombre del elemento o atributo del mensaje de instancia a entrada. Para obtener más información acerca de esta propiedad y las opciones disponibles, consulte **propiedades de vínculo de** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
-   **Vínculos de destino**. Usa el **vínculos de destino** propiedad para configurar cómo el asignador de BizTalk comparará los niveles de jerarquía de nodos. De forma predeterminada, se quita el formato a las jerarquías de esquema de origen cuando se crea el mensaje de instancia de salida. También puede decidir que desea mantener las jerarquías, haciendo coincidir los vínculos de arriba abajo o de abajo arriba. Para obtener más información acerca de esta propiedad y las opciones disponibles, consulte **propiedades de vínculo de** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
-   **Etiqueta**. Usa el **etiqueta** propiedad para crear un nombre para el vínculo más legible que el valor de XPath que se utiliza de forma predeterminada. Configurar esta propiedad resulta especialmente útil cuando se utiliza el vínculo como entrada para bucles controlados por tablas. Para obtener más información acerca de esta propiedad y las opciones disponibles y el bucle controlado por la tabla, vea **propiedades de vínculo de** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. Consulte también [bucle de tabla y Functoids de Extractor de tabla](../core/table-looping-and-table-extractor-functoids.md), respectivamente.  
  
## <a name="see-also"></a>Vea también  
  [Cómo editar propiedades de vínculo](../core/how-to-edit-link-properties.md)