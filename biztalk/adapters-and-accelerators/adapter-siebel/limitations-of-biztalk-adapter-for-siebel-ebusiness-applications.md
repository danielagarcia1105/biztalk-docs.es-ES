---
title: Limitaciones del adaptador de BizTalk para aplicaciones Siebel eBusiness | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- limitations of, Siebel adapter
- Siebel adapter, limitations of
ms.assetid: fda63dd6-bad5-4f6d-8cc1-5855efb6f063
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9018c79e910c2bfac05f07466cbeeb79ea045ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-siebel-ebusiness-applications"></a>Limitaciones del adaptador de BizTalk para Siebel eBusiness Applications
Los siguientes se conocen las limitaciones de la [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]:  
  
-   El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no es compatible con el adaptador de Microsoft BizTalk para Siebel eBusiness Applications, la versión anterior del adaptador. La versión actual del adaptador no admite enviar y recibir mensajes que tienen esquemas generados mediante la versión anterior del adaptador.  
  
    > [!NOTE]
    >  Puede modificar los proyectos de BizTalk para la versión anterior del adaptador de Siebel para utilizar el nuevo basado en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Para obtener más información, consulte [migrar BizTalk proyectos creado mediante la versión anterior del adaptador de Siebel](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).  
  
-   El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no admite objetos de flujo de trabajo.  
  
-   El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no valida el formato en el que un cliente pasa un valor de tiempo al sistema Siebel. Los clientes de adaptador deben asegurarse de que el valor especificado para un campo de fecha y hora se ajusta a un formato en el que espera el sistema Siebel.  
  
-   El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no lleva a cabo la validación del esquema. Por ejemplo, un campo de longitud 30 puede tomar valores con 100, de longitud si permitida por el sistema Siebel. También puede provocar una pérdida de datos en determinados escenarios de porque los datos que inserta el cliente a través de objetos de negocio no será necesariamente los datos que se escriben en la base de datos. Los clientes de adaptador explícitamente deben validar la entrada con respecto al esquema que obtenidas por el adaptador. Sin embargo, la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] validar que todos los campos (para los componentes empresariales) necesarios o se especifican los argumentos (para servicios de negocio).  
  
-   El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] espera que los valores de hora en formato de Siebel estándar, es decir, hh. Los valores que se especifican en cualquier otro formato producirá un error de tiempo y la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] produce una `TargetSystemException`.  
  
-   En determinados escenarios, la aplicación Siebel podría o no podría producir un mensaje de error. Por ejemplo, una operación de búsqueda mediante una expresión puede producir una excepción o devolver cero acuerdos. En consecuencia, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] podría producir un `TargetSystemException` u obtener un XML vacío como el resultado.  
  
-   Al recuperar datos desde el sistema de Siebel mediante el modelo de servicio WCF, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] deserializar XML que tienen más de 65536 nodos. Asegúrese de que la salida XML tiene nodos menor o igual que 65536. Puede evitar esta limitación si modifica el archivo app.config para la aplicación. Para obtener instrucciones, consulte [solucionar problemas de funcionamiento con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/troubleshoot-operational-issues-with-the-siebel-adapter.md).  
  
-   El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] recupera la longitud máxima para un campo de la capa de componente empresarial, en lugar de la capa de base de datos. Por lo tanto, si se intenta insertar un valor que cumpla con la longitud máxima de la columna de base de datos, pero que es mayor que la longitud máxima del campo correspondiente de un componente empresarial, el valor escrito en la base de datos podría ser diferente del valor deseara para escribir.  
  
-   Al realizar las operaciones por lotes (Insert, Update y Delete), el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] produce un error si la primera operación da como resultado un error. Sin embargo, si la primera operación se realiza correctamente y producirá un error en cualquiera de las operaciones posteriores, el adaptador no produce un error, pero en su lugar devuelve los identificadores para los registros que corresponden a las operaciones correctas en la salida. Los clientes de adaptador deben comprobar explícitamente si todas las operaciones hayan tenido éxito.  
  
-   Debido a problemas con el control de tiempo de espera por el cliente de Siebel subyacente API, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no es compatible con el tiempo de espera de conexión y comando.  
  
-   Considere un escenario donde el usuario "A" genera los metadatos para una operación de Siebel. Otro usuario "B", con menos privilegios que el usuario "A", podrá acceder a los metadatos. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no realiza ninguna comprobación para validar si el usuario "B" debe obtener acceso a los metadatos. Sin embargo, debido a privilegios suficientes, el usuario "B" no sería capaz de ejecutar cualquier operación en el sistema Siebel mediante el uso de los metadatos.  
  
-   El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no admite la especificación de un URI que incluye caracteres especiales para cualquiera de los valores de parámetros de conexión. Para cada valor de parámetro que contiene caracteres especiales, asegúrese de que reemplazar los caracteres especiales con los valores correspondientes, según lo especificado por los estándares de codificación de URI.  
  
-   Al usar los adaptadores con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], si las credenciales de WCF-Custom puerto son correctos, no se procesan los mensajes de solicitud de envío. Después de especificar las credenciales correctas, se envía el mensaje al sistema Siebel y se recibe una respuesta. Sin embargo, el mensaje de respuesta no está disponible para el puerto de salida. En estos casos, deberá reiniciar la instancia de host.  
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)