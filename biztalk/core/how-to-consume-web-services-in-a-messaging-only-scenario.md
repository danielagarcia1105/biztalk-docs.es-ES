---
title: Cómo consumir Web Services en un escenario únicamente de mensajería | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66873959-5b1b-4d9b-ad19-f083670420b8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71d1e38305fd5b798a2fa8dd59fc6341dc806dfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985453"
---
# <a name="how-to-consume-web-services-in-a-messaging-only-scenario"></a>Cómo consumir servicios web en un escenario únicamente de mensajería
Una de las nuevas mejoras del adaptador de SOAP es la capacidad de para llamar a los servicios Web en un escenario únicamente de mensajería mediante el uso de puertos de envío de enrutamiento basados en el contenido. Esta característica hace posible la consumición de servicios Web sin crear orquestaciones. Además, proporciona un mayor rendimiento para consumir servicios Web, ya que los mensajes no pasan a través de las orquestaciones.  
  
 Para consumir servicios Web en un escenario únicamente de mensajería, realice lo siguiente:  
  
-   Crear una biblioteca de proxy y esquemas XML para la invocación de servicios Web  
  
-   Configurar un puerto de envío y una ubicación de recepción para consumir un servicio Web  
  
### <a name="to-create-a-proxy-library-and-xml-schemas-for-invoking-web-services"></a>Para crear una biblioteca de proxy y esquemas XML para invocar servicios Web  
  
1. Determine la dirección URL del servicio Web.  
  
2. Abra un **proyecto vacío de servidor BizTalk** en un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solución. Para obtener más información sobre cómo crear un proyecto de BizTalk Server, consulte [cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md).  
  
   > [!NOTE]
   >  Este tutorial usa un proyecto de BizTalk Server para generar bibliotecas proxy y esquemas XML que usa el servicio Web. Además, puede usar Wsdl.exe y Xsd.exe en el SDK de .NET Framework 4.0 con el mismo fin.  
  
3. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk Server y, a continuación, haga clic en **Add Service Reference**.  
  
4. En el **Add Service Reference** cuadro de diálogo, haga clic en **avanzadas**.  
  
5. En el **configuración de referencia de servicio** cuadro de diálogo, haga clic en **Agregar referencia Web** en el **compatibilidad** sección.  
  
6. En el **Agregar referencia Web** diálogo cuadro, realice lo siguiente:  
  
   1.  En el **URL** campo, escriba una dirección URL del servicio Web y, a continuación, haga clic en **vaya**.  
  
   2.  En el **nombre de referencia Web** campo, escriba un nombre para el espacio de nombres y, a continuación, haga clic en **Agregar referencia**.  
  
7. La referencia Web aparecerá en **referencias Web** nodo en el Explorador de soluciones.  
  
   > [!TIP]
   >  Una vez que tenga una referencia web que se agrega a un proyecto de BizTalk, el **Agregar referencia Web** comando está directamente disponible cuando hace clic en el nombre del proyecto o **referencias** o **referencias Web**.  
  
8. En el Explorador de soluciones, haga clic en el nombre del proyecto y, a continuación, haga clic en **propiedades** para iniciar el Diseñador de proyectos.  
  
9. En el Diseñador de proyectos, haga clic en el **firma** ficha.  
  
10. Seleccione **firmar el ensamblado** opción, haga clic en la lista desplegable para la **elegir un archivo de clave de nombre seguro**y, a continuación, haga clic en **examinar**.  
  
11. Busque y seleccione el archivo de clave de ensamblado y, a continuación, haga clic en **abierto**.  
  
12. En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Versión de compilación**.  
  
13. En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Implementar**.  
  
### <a name="to-configure-a-send-port-and-receive-location-for-consuming-a-web-service"></a>Para configurar un puerto de envío y una ubicación de recepción para consumir un servicio Web  
  
1.  En la Consola de administración de BizTalk Server, cree un puerto de envío. Para obtener más información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Al crear el puerto de envío, seleccione SOAP como tipo o protocolo de transporte.  
  
2.  Configure el puerto de envío de SOAP con los siguientes valores de configuración. Para obtener más información, consulte [cómo configurar un puerto de envío SOAP](../core/how-to-configure-a-soap-send-port.md).  
  
    |Use|Para|  
    |--------------|----------------|  
    |**La siguiente configuración**|Seleccione esta opción para especificar las siguientes propiedades.|  
    |**Nombre del ensamblado**|Seleccione el ensamblado creado en el procedimiento anterior. El nombre completo del ensamblado se escribe en el adaptador de SOAP **AssemblyName** propiedad.|  
    |**Nombre de tipo**|Especificar el nombre de la clase que contiene el método Web que se va a invocar. El nombre de tipo se escribe en el adaptador de SOAP **TypeName** propiedad.|  
    |**Nombre del método**|Especificar uno de los métodos del cuadro de lista. El método Web se escribe en el adaptador de Soap **MethodName** propiedad.|  
  
    > [!NOTE]
    >  Si desea usar Enrutamiento por contenidos (CBR), configure el filtro del puerto de envío. Para obtener más información, consulte [cómo configurar filtros para un puerto de envío](../core/how-to-configure-filters-for-a-send-port.md).  
  
    > [!NOTE]
    >  Si no hay suscriptor para los mensajes de respuesta de los servicios Web invocados, se producirá un error en el enrutamiento.  
  
## <a name="see-also"></a>Vea también  
 [Consumo de servicios web](../core/consuming-web-services.md)