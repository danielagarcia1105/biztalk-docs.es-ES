---
title: "Cómo crear una asignación sin asignaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 520ec44f-5aca-4271-8835-b8e784214061
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81be2591c1d8f20f5b8dd01cf01c03e8daed9c9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-map-without-maps"></a>Cómo crear una asignación sin asignaciones
Si dispone de código XSLT que ha estado utilizando para convertir mensajes de instancia, puede utilizar este código directamente en vez de crear una asignación.  
  
 Utilizar el código XSLT implica crear una asignación vacía y establecer su **ruta de XSLT personalizada** propiedad de cuadrícula. Si el código XSLT utiliza ensamblados .NET externos, debe crear un archivo XML de extensión personalizada. Para obtener información sobre la estructura de un archivo XML de extensión personalizada, consulte el **XML de extensión personalizada (propiedad de cuadrícula)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="use-custom-xslt-code-in-place-of-a-map"></a>Usar código XSLT personalizado en lugar de un mapa  
  
1.  Cree una asignación de BizTalk vacía en el proyecto y establezca los esquemas de origen y destino.  
  
     Para obtener información sobre cómo crear la asignación y establecer los esquemas, vea [crear asignaciones](../core/creating-maps.md).  
  
2.  En la vista Cuadrícula, haga clic en la cuadrícula del Asignador.  
  
     Se muestra en la ventana Propiedades del **cuadrícula** propiedades.  
  
3.  En la ventana Propiedades, seleccione **ruta de XSLT personalizada** y haga clic en el botón de puntos suspensivos (**...** ) botón.  
  
4.  En el **abiertos** cuadro de diálogo, desplácese hasta el archivo y haga clic en **abiertos**.  
  
     El **ruta de XSLT personalizada** se establece la propiedad.  
  
> [!NOTE]
>  El Asignador de BizTalk solo admite XSLT 1.0. No se admite el uso de XSLT 2.0 en el Asignador de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Acerca de las asignaciones](../core/about-maps.md)   
 [Secuencias de comandos utilizando XSLT en línea y plantillas de llamada XSLT](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [XSLT personalizado](../core/custom-xslt.md)   