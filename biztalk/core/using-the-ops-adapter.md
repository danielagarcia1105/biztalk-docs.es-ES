---
title: Usar el adaptador Ops | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IOpsAIC interface
- Ops adapters, configuring
- Ops adapters, IOpsAIC interface
- process management solution tutorial, Ops adapters
- Ops adapters, processing
ms.assetid: 331f3614-e00b-4587-b82b-3c7bc394f361
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d93436e727265c4b381cdff72c42b3a677d0a4dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-ops-adapter"></a>Usar el adaptador Ops
La solución de administración de procesos empresariales utiliza el adaptador Ops para controlar informes de errores desde la nueva característica de informes de errores. La solución incluye un controlador de muestras para procesar mensajes desde el adaptador aunque puede escribir fácilmente las suyas propias y utilizar el adaptador en otras soluciones. Para obtener información acerca de la característica informes de errores, vea [enrutamiento de mensajes de error utilizando](../core/using-failed-message-routing.md).  
  
> [!NOTE]
>  Aunque la solución utiliza el adaptador para el informe de errores, su uso no se limita al control de errores. Puede utilizar el adaptador en diversas circunstancias siempre que desee ejecutar un método de objeto específico en respuesta a un mensaje.  
  
## <a name="how-the-ops-adapter-processes-error-reports"></a>Cómo procesa el adaptador OPS informes de errores  
 Puertos de la solución que usan informes de errores envían finalmente los mensajes de error para la **BizTalkErrors-SP** puerto. El filtro en el puerto comprueba la existencia de la **ErrorReport.ErrorType** propiedad de contexto. Sólo los mensajes de informes de errores tienen esta propiedad de contexto.  
  
 El **BizTalkErrors-SP** enviar puerto ejecuta el mensaje de error a través de una canalización que utiliza un componente de ensamblador XML para poner el mensaje en un sobre. A continuación, el mensaje va al adaptador Ops.  
  
 El sobre definido por el esquema ErrorEnvelope se marca para que acepte cualquier tipo de mensaje. Sin embargo, "cualquier" significa cualquier tipo de mensaje definido en el grupo de BizTalk. Esto puede producir mensajes suspendidos si la solución recibe un mensaje de un tipo desconocido. Este tipo de mensaje generaría un error y se enrutaría a la **BizTalkErrors-SP** puerto. A su vez, el mensaje generaría un error en el componente de ensamblador XML de la canalización porque no sería un tipo de mensaje conocido. El error de canalización suspende el mensaje.  
  
> [!NOTE]
>  Para controlar los errores de enrutamiento debido a tipos de mensaje desconocidos, debe escribir un componente de canalización personalizado y utilizar el componente en una canalización personalizada para la **BizTalkErrors-SP** puerto. El componente personalizado reemplaza al componente del ensamblador XML. El componente personalizado debe colocar el **ErrorReport** propiedades en el encabezado sobre y agregar el mensaje en el cuerpo de la envoltura.  
  
 El adaptador Ops es un adaptador de envío transaccional y unidireccional. Cuando el adaptador procesa un mensaje, primero carga el ensamblado especificado, de ser necesario. El adaptador almacena ensamblados en memoria caché para evitar la sobrecarga de tener que cargar el ensamblado para cada llamada. A continuación, crea una instancia de la clase especificada y, a continuación, usa la reflexión para obtener el objeto en el ensamblado que implementa el **IOpsAIC** interfaz. Si todo esto se realiza correctamente, el adaptador llama a la **inicializar** método y, a continuación, llama el **Execute** método, pasando el mensaje de informe de error.  
  
 Si se produce un error al llamar a **Execute**, el adaptador vuelve a enviar el mensaje. Si la clase especificada no implementa la **IOpsAIC** no se puede encontrar la interfaz, o la clase o un ensamblado, el adaptador suspende el mensaje.  
  
> [!TIP]
>  Como el adaptador utiliza la reflexión, el ensamblado que contiene la clase debe estar en la caché de ensamblados global (GAC).  
  
## <a name="the-iopsaic-interface"></a>La interfaz IOpsAIC  
 El adaptador requiere un objeto que implementa el **IOpsAIC** interfaz. La interfaz aparece de la siguiente forma:  
  
```  
interface IOpsAIC  
{  
    void Initialize(string config);  
    void Execute(byte[] message);  
}  
```  
  
 El adaptador pasa el mensaje original como una matriz de bytes a la **Execute** método.  
  
## <a name="configuring-the-adapter"></a>Configurar el adaptador  
 El adaptador se configura del mismo modo que cualquier otro adaptador. En la siguiente tabla se describen las propiedades de configuración del adaptador:  
  
|Nombre para mostrar|Description|  
|------------------|-----------------|  
|**Nombre seguro del ensamblado de .NET**|El nombre completo del ensamblado.|  
|**Clase OpsAIC**|El nombre de la clase en el ensamblado que implementa el **IOpsAIC** interfaz.|  
|**Datos de inicialización**|Una cadena que se pasa como argumento a la **inicializar** método de la clase.|  
  
 Observe que el adaptador requiere el nombre completo del ensamblado. El nombre completo es el nombre que se da a un ensamblado cuando lo agrega al GAC. El nombre completo es una cadena que contiene el nombre, la versión, la referencia cultural y el token de clave pública del ensamblado. Puede ver los nombres completos de los ensamblados utilizando la herramienta Caché de ensamblados global (gacutil.exe).  
  
 Para obtener más información sobre los nombres de ensamblados completos, vea "Nombres de ensamblado" en la Guía del programador de .NET Framework. Para obtener más información sobre el archivo gacutil.exe, consulte "Herramienta Caché de ensamblados global (Gacutil.exe)” en la Guía del programador de [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)].  
  
 Debe proporcionar el espacio de nombres con el nombre de clase. Por ejemplo, si la clase es **OpsHandler** en el **OperationsHandler** espacio de nombres, debe dar el nombre de clase como **OperationsHandler.OpsHandler**.  
  
## <a name="see-also"></a>Vea también  
 [El adaptador Ops](../core/the-ops-adapter.md)