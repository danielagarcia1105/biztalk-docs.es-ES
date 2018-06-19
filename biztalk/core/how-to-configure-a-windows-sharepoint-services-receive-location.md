---
title: Cómo configurar Windows SharePoint Services ubicación de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, Windows SharePoint Services adapters
- configuring [Windows SharePoint Services adapters], receive locations
- Windows SharePoint Services adapters, receive locations
ms.assetid: 5db3d5cf-4a77-4985-bd03-307c520247ec
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22a23f97634eaba9dccccd099f7c39ba6af75d67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249884"
---
# <a name="how-to-configure-a-windows-sharepoint-services-receive-location"></a>Cómo configurar una ubicación de recepción de Windows SharePoint Services
En este tema se describe cómo crear y configurar una ubicación de recepción de Windows SharePoint Services utilizando la consola de administración de BizTalk Server.  
  
### <a name="to-create-and-configure-a-windows-sharepoint-services-receive-location"></a>Para crear y configurar una ubicación de recepción de Windows SharePoint Services  
  
1.  Asegúrese de que existe un puerto de recepción debidamente configurado. Para obtener información acerca de cómo crear y configurar un puerto de recepción, vea [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  
  
2.  En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk [nombregrupo]**, expanda  **Aplicaciones**y, a continuación, expanda la aplicación que desea crear una ubicación de recepción.  
  
3.  Haga clic en **ubicaciones de recepción**, haga clic en **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
4.  Seleccione el puerto de recepción que contendrá esta ubicación de recepción y, a continuación, haga clic en **Aceptar**.  
  
5.  En el **propiedades de la ubicación de recepción** cuadro de diálogo **transporte**, en la **tipo** cuadro de lista desplegable, seleccione **Windows SharePoint Services**.  
  
6.  Haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de Windows SharePoint Services** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Puerto del servicio Web del adaptador|Puerto HTTP del sitio Web de IIS donde está instalado el servicio Web del adaptador de Windows SharePoint Services. De forma predeterminada, este es el sitio de Web predeterminado configurado en el puerto 80. Si ha configurado el servicio Web de Windows SharePoint Services en cualquier sitio Web de IIS que no sea el sitio Web predeterminado, tendrá que actualizar este valor.|  
    |Timeout|Tiempo de espera, en milisegundos, de las llamadas del servicio Web de tiempo de ejecución del adaptador que se realizan al servicio Web del adaptador de Windows SharePoint Services. Puede que tenga que aumentar este valor si el tamaño del mensaje o del lote es mayor que el promedio que espera el adaptador.|  
    |Nombre del archivo|(Opcional) Nombre del archivo de Windows SharePoint Services. Puede escribir un valor literal como 'PurchaseOrder0001.xml' o una expresión. Las expresiones pueden incluir cualquier combinación de valores literales, macros y consultas XPATH. Por ejemplo, "Pedido-%XPATH=//pd:IdPedido%-%IdMensaje%.xml". Si no especifica el nombre de archivo, se utilizará el nombre del archivo de origen. Para obtener más información acerca de las expresiones, vea [expresiones del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-expressions.md). **Nota:** el "% SendingOrchestrationID %" y "% SendingOrchestrationType %" macros no son compatibles con este campo.|  
    |Dirección URL de ubicación de archivado|URL de la carpeta Windows SharePoint Services, asociada al sitio de SharePoint, en la que se procesan los archivos almacenados. Por ejemplo, Archivo o /Documentos compartidos/Pedidos procesados/. Si no se especifica una ubicación de archivado, el documento se eliminará tras haber sido procesado por el adaptador. **Nota:** en ocasiones la biblioteca de documentos de SharePoint o una carpeta de dirección URL es distinta del nombre de ese elemento. Compruebe la barra de direcciones de Internet Explorer para conocer la dirección URL correcta.|  
    |Sobrescribir archivo|Determina si deben o no sobrescribirse los archivos almacenados. Seleccione "Sí" para sobrescribir los archivos existentes. Seleccione "No" para que el archivo genere un error en caso de que se haya almacenado otro archivo con el mismo nombre. En este caso, el archivo permanecerá desprotegido y deberá almacenarse manualmente. **Nota:** para archivar los archivos, se recomienda usar los valores del nombre del archivo con macros con el fin de que el nombre de archivo sea único. Para este fin, podría utilizar un valor Nombre del archivo, por ejemplo Pedido-%IdMensaje%.xml o Pedido-%XPATH=//ns0:Pedido/ns0:Id%.xml, donde Id. sea el identificador exclusivo del pedido.|  
    |Tamaño del lote|Número máximo de documentos que procesará en un solo lote el servicio Web del adaptador de mensajería de Windows SharePoint Services. Un lote procesado podría contener menos mensajes de los definidos en el tamaño del lote, pero nunca podrá contener más mensajes.|  
    |Error de umbral|Número máximo de errores de sondeo consecutivos que detecta el adaptador hasta que se deshabilita la ubicación de recepción. Defina este campo como 0 para no deshabilitar nunca la ubicación de recepción.|  
    |Alias de espacios de nombres|(Opcional) Lista separada por comas o punto y coma de definiciones de alias de espacios de nombres. Utilice este campo para definir los alias de espacio de nombres utilizados en las consultas XPATH que se han introducido en el campo Nombre del archivo. Por ejemplo, po='http://OrderProcess/POrder', conf='http://OrderProcess/Confirmation' ipsol='{D8217CF1-4EF7-4bb5-A30D-765ECB09E0D9}'|  
    |Intervalo de sondeo|Intervalo de tiempo, en segundos, entre dos consultas consecutivas realizadas por el adaptador para determinar si hay mensajes nuevos por procesar. **Nota:** especificando un valor inferior mejora el rendimiento y tiempo de respuesta para el adaptador.|  
    |Dirección URL del sitio de SharePoint|Dirección URL completa del sitio Web de Windows SharePoint Services. Por ejemplo, http://BizTalkServer/sites/TestSite. **Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres.|  
    |Dirección URL de la biblioteca de documentos de origen|URL de la biblioteca de documentos de Windows SharePoint Services, asociada al sitio SharePoint, en la que se recuperan los documentos. Por ejemplo, /Documentos compartidos/ o /Pedidos nuevos/. **Nota:** no puede recibir mensajes de una lista de SharePoint. No podrá recibir mensajes desde una carpeta de SharePoint a menos que utilice una vista en la que se muestren los mensajes de todas las carpetas. Para ello, establecer el **carpetas** en un valor de **mostrar todos los documentos sin carpetas** al crear una vista. **Nota:** a veces es distinta del nombre de ese elemento de la biblioteca de documentos de SharePoint. Compruebe la barra de direcciones de Internet Explorer para conocer la dirección URL correcta.|  
    |Nombre de vista|Vista de Windows SharePoint Services que se utiliza para filtrar los documentos procesados por el adaptador. Por ejemplo, Pedidos aprobados. Deje este campo en blanco para procesar todos los documentos existentes en la biblioteca de documentos de origen. El adaptador no procesará las carpetas que aparecen en una vista, ni los mensajes que contengan dichas carpetas. Puede crear vistas planas que muestren todos los documentos en una estructura plana, incluidos los documentos de las subcarpetas. **Nota:** se procesarán todos los mensajes en una vista plana.|  
    |Integración con Microsoft Office|"Opcional" para intentar quitar las instrucciones de procesamiento de InfoPath si es posible, o procesarlas como están en caso contrario (por ejemplo, en el caso de un documento binario). Seleccione "Sí" para quitar las instrucciones de procesamiento de InfoPath o pasar por alto el mensaje en caso de error. Seleccione "No" para procesar el documento "tal cual". Para mensajes binarios, se deben usar los valores “No” y “Opcional”.|  
  
8.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar un controlador de envío de Windows SharePoint Services](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [Cómo configurar un puerto de envío de Windows SharePoint Services](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [Cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md)   
 [Referencia de propiedades de adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Expresiones del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-expressions.md)   
 [Admite los tipos de columna de Windows SharePoint Services](../core/supported-windows-sharepoint-services-column-types.md)