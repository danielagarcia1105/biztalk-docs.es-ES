---
title: Cómo configurar la validación de asignaciones y parámetros de prueba | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1768918c-e94f-476f-b288-9e030c691177
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7aaa62e74f1c49f2e43d96c7d546af023847d91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967413"
---
# <a name="how-to-configure-map-validation-and-test-parameters"></a>Cómo configurar la validación de asignaciones y parámetros de prueba
Antes de validar y comprobar una asignación, deberá establecer la asignación de parámetros de prueba y validación el **propiedades** ventana del mapa.  
  
## <a name="configure-the-map-validation-and-test-parameters"></a>Configurar los parámetros de prueba y validación de mapa  
  
1.  En el Explorador de soluciones, haga clic en la asignación cuya página de propiedades que desea configurar y, a continuación, haga clic en **propiedades**.  
  
2.  En la ventana Propiedades, haga lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Validar entrada de comprobar asignación**|Configurar si quiere o no que se valide el mensaje de instancia con respecto al esquema de origen antes de comprobar la asignación.|  
    |**Validar salida de comprobar asignación**|Configurar si quiere o no que se valide el mensaje de instancia con respecto al esquema de destino después de comprobar la asignación.|  
    |**Instancia de entrada de comprobar asignación**|Configurar la ubicación de los datos del mensaje de instancia que se va a utilizar cuando compruebe la asignación.<br /><br /> Si configura esta propiedad, también debe configurar el **entrada de comprobar asignación** propiedad.|  
    |**Instancia de salida de comprobar asignación**|Configure la ubicación del archivo donde desea que se almacene la salida de la operación de comprobar asignación.<br /><br /> Si configura esta propiedad, también debe configurar el **salida de comprobar asignación** propiedad.|  
    |**Entrada de comprobar asignación**|Configurar el formato de datos de instancia de entrada.|  
    |**Salida de comprobar asignación**|Configurar el tipo de datos de salida que se va a utilizar cuando compruebe la asignación.|  
  
    > [!IMPORTANT]
    >  Si desea comprobar la asignación, debe configurar en primer lugar las propiedades de la asignación.  

Una vez que haya desarrollado la asignación, uno de los siguientes pasos es validarla. En este tema se proporcionan instrucciones detalladas para validar asignaciones.  
  
## <a name="validate-a-biztalk-map"></a>Validar una asignación de BizTalk  
  
1.  En el Explorador de soluciones, abra la asignación que desee validar.  
  
2.  En el Explorador de soluciones, haga clic en el mapa y, a continuación, seleccione **validar asignación**.  
  
3.  En el **salida** ventana, compruebe los resultados.  
  
> [!IMPORTANT]
>  Si en la salida utiliza constantes o datos personalizados, debe comprobar que los tipos de datos de los datos de prueba de origen y los valores constantes de destino sean válidos. Cuando se valida una asignación, el Asignador de BizTalk no comprueba si los datos de instancia infringen los tipos de datos definidos en los esquemas. Esto se hace cuando prueba la asignación o valida los datos de instancia con el Editor de BizTalk. 

## <a name="test-a-biztalk-map"></a>Probar una asignación de BizTalk

Una vez que haya desarrollado la asignación, uno de los siguientes pasos es comprobarla. Este tema proporciona instrucciones paso a paso para probar asignaciones, incluido los pasos para ver el XSLT generado por el compilador de asignaciones.  
  
1.  En el Explorador de soluciones, haga clic en el mapa que desee probar y, a continuación, seleccione **comprobar asignación**.  
  
2.  Comprobar los resultados en el **salida** ventana.  
  
    > [!IMPORTANT]
    >  Es recomendable que configure las propiedades de instancia de entrada y de salida en la ventana Propiedades antes de comprobar una asignación.  
  
## <a name="review-the-xslt"></a>Revisar el XSLT  
 A menudo es útil inspeccionar el XSLT generado por el compilador de asignaciones. Algunas de las ventajas de inspeccionar un XSLT son:  
  
- Si está utilizando functoids de bucle o personalizados, sabrá mejor cómo se realiza el bucle y cómo se invoca el functoid personalizado.  
  
- Si tiene una asignación complicada, revisar el XSLT le permitirá ver cómo se traduce la asignación a una transformación y puede proporcionar información sobre cómo mejor estructura, sustitución o eficacia de una o más partes.  
  
- Si está usando secuencias de comandos personalizadas u otros artefactos, revisar el XSLT le permitirá ver cómo interactúan las secuencias de comandos, artefactos y otras partes de la asignación.  
  
  Es decir, revisar el XSLT es un buena forma de depurar una asignación.  
  
#### <a name="view-the-xslt-generated-by-the-map-compiler"></a>Ver el XSLT generado por el compilador de asignaciones  
  
1.  En un proyecto de BizTalk de Visual Studio, seleccione el **el Explorador de soluciones** pestaña, haga clic en un mapa y, a continuación, seleccione **validar asignación**.  
  
2.  Desplácese a la ventana Resultados para buscar la dirección URL del archivo XSL. Presione **CTRL**y seleccione la dirección URL para ver el archivo.  
  
> [!NOTE]
>  Los cambios realizados en el archivo XSL no se reflejan en el mapa y se sobrescriben en la siguiente compilación.  
  
## <a name="see-also"></a>Vea también  

[Cómo depurar asignaciones](../core/how-to-debug-maps.md)  
[Solución de problemas de mapas](../core/troubleshooting-maps.md)  