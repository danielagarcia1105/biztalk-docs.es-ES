---
title: Enlaces de puerto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, warnings
- ports, bindings
- bindings, Web ports
- bindings, design time
- Web ports, port bindings
- bindings, ports
- bindings, direct
- bindings, warnings
- bindings, deployment
- bindings, dynamic
ms.assetid: b61c725a-0082-42d3-b88a-533583161734
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 943cbbaa6db9413ffad15bfcf3302d2216e3ab17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265204"
---
# <a name="port-bindings"></a>Enlaces de puerto
Un enlace de puerto es la información de configuración que determina dónde y cómo se enviará o recibirá un mensaje. Según el tipo, es posible que un enlace de puerto haga referencia a ubicaciones físicas, canalizaciones u otras orquestaciones.  
  
 Hay tres tipos de enlaces de puertos para puertos que reciben mensajes:  
  
-   Especificar ahora  
  
-   Especificar más tarde  
  
-   Directo  
  
 Hay cuatro tipos de enlaces de puertos para puertos que envían mensajes:  
  
-   Especificar ahora  
  
-   Especificar más tarde  
  
-   Directo  
  
-   Dinámica  
  
## <a name="binding-at-deployment-time"></a>Enlace en tiempo de implementación  
 Puede enlazar el puerto con una ubicación de recepción o con un puerto de envío. Si no tiene toda la información que se debe especificar una ubicación física, puede seleccionar la **especificar más tarde** opción de enlace de puerto en el Diseñador de orquestaciones y solo hay que especificar el tipo de puerto que describe el puerto. Una vez que se ha implementado la aplicación, puede especificar la información acerca de la ubicación mediante el uso de la Consola de administración de BizTalk o puede configurar la información de configuración mediante programación.  
  
## <a name="binding-at-design-time"></a>Enlace en tiempo de diseño  
 Puede seleccionar la **especificar ahora** puerto opción de enlace en el Diseñador de orquestaciones para especificar el transporte y la canalización en tiempo de diseño. Al especificar el puerto para la recepción de mensajes, solo están disponibles los transportes HTTP, SOAP y FILE en la lista desplegable. Al especificar el puerto para el envío de mensajes, solo están disponibles los transportes HTTP, FILE y SMTP en la lista desplegable. Esta opción es útil si conoce previamente el origen o el destino de los mensajes transmitidos.  
  
## <a name="direct-binding"></a>Enlace directo  
 Los puertos de enlace directo son puertos lógicos unidireccionales y bidireccionales en las orquestaciones que no están enlazadas expresamente a ningún puerto físico. Los puertos de enlace directo permiten tener distintos patrones de comunicación entre los servicios. Para implementar el enlace directo, seleccione la **directa** puerto opción de enlace en el Diseñador de orquestaciones en tiempo de diseño.  
  
 Hay tres tipos de puertos de enlace directo:  
  
-   Puerto de enlace directo de cuadro de mensajes  
  
-   Puerto de enlace directo de autocorrelación  
  
-   Puerto de enlace directo de orquestación de socio  
  
 Para obtener más información sobre cómo trabajar con puertos de enlace directo, vea [trabajar con puertos de enlace directo en orquestaciones](../core/working-with-direct-bound-ports-in-orchestrations.md).  
  
> [!NOTE]
>  Si utiliza el enlace directo, no podrá intercambiar mensajes entre un puerto de solicitud-respuesta y dos puertos unidireccionales.  
  
> [!NOTE]
>  El enlace directo no es compatible con los estándares del Lenguaje de ingeniería de procesos empresariales para servicios Web (BPEL4WS). Si necesita compatibilidad con BPEL4WS, use otro tipo de enlace.  
  
## <a name="dynamic-binding"></a>Enlace dinámico  
 Si no conocerá el destino de una comunicación hasta el tiempo de ejecución, puede usar el enlace dinámico para un puerto de envío. La ubicación podría, por ejemplo, se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en el **expresión** forma, tal y como se muestra en el código siguiente:  
  
```  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="mailto:johnd@contoso.com";  
```  
  
 Para obtener información acerca de cómo asignar dinámicamente los valores a puertos, consulte [cómo asignar valores a puertos dinámicos](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md).  
  
## <a name="web-ports"></a>Puertos Web  
 Si el proyecto contiene una referencia a un servicio Web, el Diseñador de orquestaciones lo detectará y hará que esté disponible un tipo de puerto Web apropiado. Para crear un puerto Web, solo tiene que agregar un puerto a la orquestación y asignarle un tipo de puerto Web existente. Para obtener más información, consulte [crear puertos Web](../core/creating-web-ports.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo trabajar con tipos de puerto](../core/how-to-work-with-port-types.md)   
 [Patrón de comunicación](../core/communication-pattern.md)   
 [Dirección de comunicación](../core/communication-direction.md)   
 [Uso de puertos en orquestaciones](../core/using-ports-in-orchestrations.md)   
 [Cómo ejecutar al Asistente para configuración de puertos](../core/how-to-run-the-port-configuration-wizard.md)   
 [Consumir servicios Web](../core/consuming-web-services.md)