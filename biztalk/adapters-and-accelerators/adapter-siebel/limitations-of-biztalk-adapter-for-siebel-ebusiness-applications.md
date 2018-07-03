---
title: Limitaciones del adaptador de BizTalk para aplicaciones Siebel eBusiness | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- limitations of, Siebel adapter
- Siebel adapter, limitations of
ms.assetid: fda63dd6-bad5-4f6d-8cc1-5855efb6f063
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e47e558ccf0d9841c47911490c1cee319515fd90
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019448"
---
# <a name="limitations-of-biztalk-adapter-for-siebel-ebusiness-applications"></a>Limitaciones del adaptador de BizTalk para aplicaciones Siebel eBusiness
Lo siguiente es limitaciones conocida de la [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]:  
  
- El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no es compatible con el adaptador de Microsoft BizTalk para Siebel eBusiness Applications, la versión anterior del adaptador. No admite la versión actual del adaptador de envío y recepción de mensajes que tienen esquemas generados mediante el uso de la versión anterior del adaptador.  
  
  > [!NOTE]
  >  Puede modificar los proyectos de BizTalk para la versión anterior del adaptador de Siebel para utilizar el nuevo basado en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Para obtener más información, consulte [migrar BizTalk proyectos creado mediante la versión anterior del adaptador de Siebel](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).  
  
- El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no admite objetos de flujo de trabajo.  
  
- El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no valida el formato en el que un cliente pasa un valor de tiempo al sistema Siebel. Los clientes del adaptador deben asegurarse de que el valor especificado para un campo de fecha y hora se ajusta a un formato en el que espera que el sistema Siebel.  
  
- El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no lleva a cabo la validación del esquema. Por ejemplo, un campo de longitud 30 puede tomar valores con 100, longitud si permitida por el sistema Siebel. También puede provocar una pérdida de datos en determinados escenarios que los datos que inserta el cliente a través de objetos de negocios no necesariamente los datos que se escriben en la base de datos. Los clientes del adaptador deben validar explícitamente la entrada con respecto al esquema que aparece por el adaptador. Sin embargo, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] validar que todos los campos (para los componentes empresariales) de necesarios o que se especifican argumentos (para servicios de negocio).  
  
- El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] espera que los valores de hora se especifiquen en el formato estándar de Siebel, que es HH: mm:. Valores de hora que se especifican en cualquier otro formato, producirá un error, y el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] produce una `TargetSystemException`.  
  
- En determinados escenarios, la aplicación Siebel podría o no puede producir un mensaje de error. Por ejemplo, una operación de búsqueda mediante una expresión podría producir una excepción o devolver cero acuerdos. En consecuencia, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] podría producir un `TargetSystemException` u obtener un XML vacío como salida.  
  
- Al recuperar datos desde el sistema de Siebel mediante el modelo de servicio WCF, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] deserializar archivos XML que tienen más de 65536 nodos. Asegúrese de que la salida XML tiene nodos menor o igual a 65536. Puede evitar esta limitación si modifica el archivo app.config para su aplicación. Para obtener instrucciones, consulte [solución de problemas operativos con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/troubleshoot-operational-issues-with-the-siebel-adapter.md).  
  
- El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] recupera la longitud máxima de un campo de la capa del componente empresarial, en lugar de la capa de base de datos. Por lo tanto, si se intenta insertar un valor que cumple con la longitud máxima de la columna de base de datos, pero que es mayor que la longitud máxima del campo correspondiente para un componente empresarial, el valor escrito en la base de datos podría ser diferente del valor deseara para escribir.  
  
- Al realizar las operaciones por lotes (Insert, Update y Delete), el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] produce un error si la primera operación da como resultado un error. Sin embargo, si la primera operación se realiza correctamente y producirá un error en cualquiera de las operaciones subsiguientes, el adaptador no produce un error, pero en su lugar devuelve los identificadores de los registros correspondientes a las operaciones correctas en la salida. Los clientes del adaptador deben comprobar explícitamente si todas las operaciones han tenido éxito.  
  
- Debido a problemas con el control de tiempo de espera por el cliente de Siebel subyacente API, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no es compatible con el tiempo de espera de conexión y comando.  
  
- Considere un escenario donde el usuario "A" genera los metadatos de una operación en Siebel. "B", que tenga privilegios de menor que "A", un usuario de otro usuario podrá acceder a los metadatos. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no realiza ninguna comprobación para validar si el usuario "B" debe obtener acceso a los metadatos. Sin embargo, por falta de privilegios, es posible que el usuario "B" no ser capaz de ejecutar cualquier operación en el sistema Siebel mediante el uso de los metadatos.  
  
- El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no admite la especificación de un URI que incluye caracteres especiales para cualquiera de los valores de parámetro de conexión. Para cada valor de parámetro que contiene caracteres especiales, asegúrese de que reemplazar los caracteres especiales con los valores correspondientes, según lo especificado por los estándares de codificación de URI.  
  
- Al usar los adaptadores con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], si las credenciales en el WCF-Custom puerto son incorrectos, no se procesan los mensajes de solicitud de envío. Después de especificar las credenciales correctas, el mensaje se envía al sistema Siebel y se recibe una respuesta. Sin embargo, el mensaje de respuesta no está disponible para el puerto de salida. En estos escenarios, es posible que deberá reiniciar la instancia de host.  
  
## <a name="see-also"></a>Vea también  
 [Definición del adaptador de BizTalk para las aplicaciones de negocio electrónico de Siebel](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)