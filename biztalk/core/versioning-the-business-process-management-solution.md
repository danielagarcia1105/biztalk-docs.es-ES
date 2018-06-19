---
title: Control de versiones de la solución de administración de procesos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- versioning, process management solutions
- process management solution tutorial, modifying
- process management solution tutorial, versioning
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 501b2162-821f-44e1-87c0-8628cc5bd9c3
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af8afd3666a35b827ff25b243c1bfb4c81262273
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288652"
---
# <a name="versioning-the-business-process-management-solution"></a>Control de versiones de la solución de administración de procesos empresariales
La solución Administración de procesos empresariales está diseñada para poder reemplazar las fases si es necesario. El diseño proporciona también un método fácil de crear versiones de esquemas.  
  
 Para obtener información acerca de cómo dividir un proceso empresarial en fases, vea [algunos principios de diseño de la solución de administración de procesos empresariales](../core/some-design-principles-in-the-business-process-management-solution.md).  
  
> [!NOTE]
>  Los elementos de la solución son altamente dependientes de las estructuras de mensajes. Para cambiar estructuras de mensajes, es preciso realizar cambios sustanciales en las orquestaciones.  
  
 Para obtener instrucciones generales acerca de cómo actualizar ensamblados en una solución implementada y directrices para escribir scripts para administrar la actualización, vea [actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md).  
  
## <a name="adding-replacing-or-removing-stages"></a>Agregar, reemplazar o quitar fases  
 Las orquestaciones de la fase de procesamiento de pedidos contienen dos tipos de código: el código que implementa el proceso empresarial y el código que proporciona la infraestructura para que puedan funcionar en la solución. En las orquestaciones de la fase, **CableOrder1** y **CableOrder2**, el código de proceso de negocio dentro de una forma Agrupar con la etiqueta "Procesamiento empresarial".  
  
 La forma más fácil de crear una nueva fase es copiar una de las fases, reemplazar el código del grupo "Procesamiento empresarial" por su código y dejar el código de infraestructura intacto.  
  
> [!NOTE]
>  El **CableOrder2** orquestación tiene dos grupos "Procesamiento empresarial", el segundo en torno a la forma de actualizar el historial de envío. La forma Envío es parte de un eficaz ámbito de envío. (Para obtener más información, vea "Mejorar el rendimiento con ámbitos anidados" en [de procesamiento en la orquestación OrderBroker](../core/processing-in-the-orderbroker-orchestration.md).) Puesto que una forma Grupo no se puede superponer a una parte de una forma de ámbito, se pone una etiqueta al segundo grupo para indicar que forma parte del código de proceso empresarial.  
  
 Debe establecer la expresión de filtro de la nueva orquestación en su número en la secuencia. El **OrderManager** supone números de fase comienzan con uno y aumenta en uno por cada fase siguiente (1, 2, 3...). Para filtrar una tercera fase, debe establecer la expresión de filtro del siguiente modo:  
  
 `(Microsoft.Samples.BizTalk.SouthridgeVidoe.Schemas.Stage == 3)`  
  
 La solución utiliza la API de SAE para realizar un seguimiento de los sucesos de la solución, incluidas las fases de procesamiento de pedidos. La primera fase comienza la actividad de SAE y la última fase la finaliza. Si se producen excepciones, los controladores de la solución terminan las actividades de SAE implicadas. SAE vuelve a ensamblar de forma eficaz las operaciones interrumpidas en una vista continua para supervisión.  
  
## <a name="changing-configuration"></a>Cambiar la configuración  
 Si los cambios aumentan o reducen el número de fases, debe cambiar la información de configuración almacenada en el almacén del secreto de inicio de sesión único (SSO) empresarial.  
  
 Si no ha implementado la aplicación, puede modificar la opción de configuración para **TotalStages** en el archivo de secuencia de comandos CreateSouthridgeVideoApplication.cmd. El valor cambiará cuando se ejecute la secuencia de comandos durante la implementación.  
  
 Si ya ha implementado la aplicación, puede cambiar el valor ejecutando una utilidad de la línea de comandos, BTSScnSSOApplicationConfig, en la carpeta SDK\Common\SsoApplicationConfig. Para establecer el número total de fases en tres, utilice la siguiente línea de comandos:  
  
 `BTSScnSSOApplicationConfig -set SouthRidgeVideo.CableOrder ConfigProperties TotalStages 3`  
  
 Puesto que la solución almacena en caché los valores de configuración, debe esperar hasta que pase el intervalo de actualización para que surta efecto el nuevo valor.  
  
## <a name="versioning-schemas"></a>Control de versiones de esquemas  
 BizTalk toma un esquema de la versión más reciente del ensamblado que lo contiene. Esto significa que, si crea una nueva versión de un esquema, reemplaza totalmente todas las versiones anteriores del esquema. Esto funciona bien cuando las transacciones duran poco. Sin embargo, las transacciones en la solución de administración de procesos empresariales son de larga duración: un pedido puede tardar un año en completarse.  
  
 Para permitir la posibilidad de usar varias versiones de un esquema en uso, cada esquema de la solución incluye un número de versión en su espacio de nombres. Por ejemplo, el espacio de nombres del esquema Order es el siguiente:  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 Puesto que el espacio de nombres identifica el esquema y la inclusión del número de versión hace que el espacio de nombres sea único del esquema, el nuevo esquema será distinto de la versión anterior. Por tanto, se puede usar un nuevo esquema sin suplantar el esquema anterior.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar una solución de administración de procesos empresariales](../core/developing-a-business-process-management-solution.md)