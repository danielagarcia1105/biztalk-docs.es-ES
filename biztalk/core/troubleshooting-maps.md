---
title: Solucionar problemas de asignaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32e2eb52-6740-4cf5-82ec-3b6d0b784276
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bb7b3dc8356172989c215dc13e5fd82e46f4689
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-maps"></a>Solución de problemas de los mapas
En este tema se proporcionan estrategias de solución de problemas, así como detalles de problemas de las asignaciones e información para su resolución.  
  
## <a name="troubleshooting-strategies"></a>Estrategias de solución de problemas  
  
### <a name="validate-your-map"></a>Validar su asignación  
 Aunque puede parecer obvio, debería validar siempre su asignación en diferentes momentos durante su desarrollo. De este modo, será más fácil identificar problemas de diseño, lógica y esquema en fases tempranas del ciclo de desarrollo cuando es más sencillo solucionarlos o encontrar una solución alternativa.  
  
##### <a name="to-validate-a-biztalk-map"></a>Para validar una asignación de BizTalk  
  
1.  En el Explorador de soluciones, abra la asignación que desee validar.  
  
2.  En el Explorador de soluciones, haga clic en el mapa y, a continuación, haga clic en **validar asignación**.  
  
3.  Compruebe los resultados en la ventana Resultados.  
  
> [!NOTE]
>  Cuando se valida una asignación, los datos de la instancia de prueba no se comprueban para ver si infringen los tipos de datos definidos en los esquemas. Los datos de instancia se comprueban cuando prueba la asignación o valida los datos de instancia en el Editor de BizTalk.  
  
### <a name="review-the-xslt-generated-for-your-map"></a>Revisar el XSLT generado para la asignación  
 A menudo es útil inspeccionar el XSLT generado por el compilador de asignaciones. Algunas de las ventajas de inspeccionar un XSLT son:  
  
-   Si está utilizando functoids de bucle o personalizados, sabrá mejor cómo se realiza el bucle y cómo se invoca el functoid personalizado.  
  
-   Si tiene una asignación complicada, revisar el XSLT le permitirá ver cómo se traduce la asignación a una transformación y le puede dar nociones acerca de cómo se puede conseguir una mejor estructura, sustitución o eficacia de una o más partes.  
  
-   Si está usando secuencias de comandos personalizadas u otros artefactos, revisar el XSLT le permitirá ver cómo interactúan las secuencias de comandos, artefactos y otras partes de la asignación.  
  
 Afortunadamente, ver el XSLT de una asignación es un proceso sencillo.  
  
##### <a name="to-view-the-xslt-generated-by-the-map-compiler"></a>Para ver el XSLT generado por el compilador de asignaciones  
  
1.  Desde un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, haga clic en el **el Explorador de soluciones** pestaña, haga clic en un mapa y, a continuación, haga clic en **validar asignación**.  
  
2.  Desplácese a la ventana Resultados para buscar la dirección URL del archivo XSL. Presione CTRL y haga clic en la dirección URL para ver el archivo.  
  
 Si decide personalizar la asignación a mano, puede modificar la versión que el compilador de asignaciones ha producido. El Asignador no reflejará los cambios y éstos se perderán la siguiente vez que cree la solución.  
  
### <a name="tune-your-map-for-specific-scenarios-using-mapsource"></a>Ajuste la asignación para determinados escenarios mediante \<mapsource\>  
 Puede modificar algunos comportamientos predeterminados del asignador mediante la modificación de atributos de la **mapsource** elemento directamente en un archivo de origen (.btm) de asignación. Hay tres comportamientos que puede modificar:  
  
-   **Optimizar la generación de código de functoid de asignación de valores**. También puede modificar el comportamiento que controla cuando se usa una variable con `if` instrucciones.  
  
-   **Dar cabida a esquemas con huellas grandes**. Puede cambiar el modo en que se usan los nodos del compilador interno en asignaciones grandes.  
  
-   **Administrar el uso de for-each con functoids de bucle condicional y asignación de valores**. Puede controlar dónde el `xsl:for-each` instrucción se usa en el esquema de destino.  
  
 Para obtener más información acerca de cómo modificar **mapsource**, consulte [administrar usando de comportamiento en el asignador predeterminado \<mapsource\>](../core/managing-default-mapper-behavior-using-mapsource.md).  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de preguntas y respuestas de general](../core/general-troubleshooting-questions-and-answers.md)   
 [Errores comunes](../core/common-errors.md)