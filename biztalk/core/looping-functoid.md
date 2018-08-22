---
title: Functoid de bucle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19886ccb-4642-48a4-b93e-563640ea828b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ce2b66fd796708a0e8b24ee05e3a0b043af6808
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22262844"
---
# <a name="looping-functoid"></a>Bucle (functoid)

## <a name="overview--example"></a>Información general sobre & ejemplo
El **bucle** functoid combina múltiples registros o campos del esquema de origen en un único registro del esquema de destino.  
  
 La siguiente ilustración muestra un **bucle**functoid usado en una asignación para combinar direcciones recopiladas de dos encuestas diferentes en una lista de direcciones maestra única.  
  
> [!NOTE]
>  El **bucle** y **asignación de valores (sin formato)** functoids no deben usarse juntos. Si ambos se usan conjuntamente, se produce una asignación compilada que supone que no hay dependencia de los nodos de destino que están por debajo de bucle de origen el **bucle** functoid.  
  
 ![Mapa que ilustra el uso del functoid de bucle. ](../core/media/loopingfunctoid.gif "loopingfunctoid")  
  
 El **FoodSurvey** y **FlowerSurvey** registros de bucle del esquema de origen se asignan a los bucles **dirección** registro del esquema de destino. Si un mensaje de instancia de entrada tiene tres **FoodSurvey** y dos registros **FlowerSurvey** registros, la **bucle**functoid combina estos elementos para crear cinco  **Dirección** registros en el mensaje de instancia de salida.  
  
 El siguiente código es un mensaje de instancia de entrada de ejemplo.  
  
```  
<ns0:Surveys xmlns:ns0="http://LoopingFunctoid.Surveys">  
    <FoodSurvey Name="Karin Zimprich" Address="345 N 63rd St" City="Boston" State="MA" PostalCode="07485" />  
    <FoodSurvey Name="Wendy Wheeler" Address="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" />  
    <FoodSurvey Name="Florian Voss" Address="1234 Main St" City="Denver" State="CO" PostalCode="97402" />  
    <FlowerSurvey Name="Kelly Focht" Address="456 1st Ave" City="Miami" State="FL" PostalCode="81406" />  
    <FlowerSurvey Name="Jim Kim" Address="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" />  
</ns0:Surveys>  
```  
  
 Este mensaje de instancia de entrada produce el siguiente mensaje de instancia de salida cuando lo procesa una asignación en la ilustración anterior.  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 El **FoodSurvey** y **FlowerSurvey** han combinado las direcciones de mensaje. El mensaje combinado no indica el origen de cada dirección. Si desea realizar un seguimiento del origen, agregue un **origen** atribuir a la **dirección** registros de la **MasterAddress** esquema y asignar un valor constante. Para establecer este valor, conecte el **FoodSurvey** campo a la nueva **origen** campo. En la línea de conexión, modifique la **propiedades de vínculo de** &#124; **compilador** &#124; **vínculos de origen** propiedad a "Copiar nombre". Repita este proceso para el **FlowerSurvey** campo. Volver a procesar el mensaje de entrada anterior produce el resultado siguiente:  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458" Source="FoodSurvey"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" Source="FoodSurvey"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402" Source="FoodSurvey"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406" Source="FlowerSurvey"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" Source="FlowerSurvey"/>  
</ns0:MasterAddresses>  
```  

## <a name="relationships-with-nodes"></a>Relaciones con nodos

 Las relaciones entre nodos afectan al comportamiento de la **bucle** functoid. Por ejemplo, vincular un nodo secundario y su entidad primaria en el esquema de origen el **bucle** functoid impide que el nodo de destino que se está creando.  
  
 También se ven afectados los functoids por las relaciones entre los nodos de origen. Conectar un functoid a campos secundarios de diferente nivel de nodos de origen de la **bucle** functoid puede producir resultados inesperados. Por ejemplo, si se usa el **concatenación de cadenas** functoid para combinar el **FoodSurvey** campo de nombre y **FlowerSurvey** campo de dirección en el campo de nombre de dirección en **MasterAddress** generaría el siguiente mensaje de instancia de salida:  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 Observe cómo la **nombre** campo no está presente para **FoodSurvey** origen mensajes pero está presente para **FlowerSurvey** mensajes de origen.  
  
> [!IMPORTANT]
>  Conectar un functoid a campos secundarios de nodos de origen de la **bucle** functoid puede producir resultados inesperados si los nodos de origen no son del mismo nivel.  
  
 El **bucle** functoid es una eficaz construcción que puede usar para crear bucles condicionales y asignar esquemas a catálogos. También hay algunos efectos de superpuestas **bucle** rutas de functoid debe tener en cuenta.  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Bucles condicionales](../core/conditional-looping.md)  
  
-   [De esquema sin formato a catálogo](../core/flat-schema-to-catalog.md)  
  
-   [Rutas de acceso de bucles](../core/loop-paths.md)  
  
## <a name="see-also"></a>Vea también  
 **Referencia de Functoid de bucle de tabla** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]