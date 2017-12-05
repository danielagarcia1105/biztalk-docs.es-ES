---
title: API de BAM (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, APIs
- examples, BAM
- BAM, examples
- APIs, BAM
ms.assetid: 32a925f2-c7f4-4111-9c59-8865f15c6a89
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f65b98871f054d96caa278e48de19ad669157b1f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="bam-api-biztalk-server-sample"></a>API de BAM (ejemplo de BizTalk Server)
El ejemplo de API de BAM ilustra el modo de incorporar llamadas a la API de BAM en una aplicación para guardar información de claves que podrá supervisar.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En este ejemplo se implementa un escenario simple de compra. Genera pedidos de compra, procesa cada pedido de compra, crea envíos y crea y procesa facturas. Según se ejecuta el ejemplo, crea y actualiza actividades BAM para reflejar los detalles y la disposición de los pedidos de compra y facturas.  
  
## <a name="how-this-sample-was-designed-and-why"></a>Cómo y por qué se ha diseñado este ejemplo  
 Este ejemplo se ha diseñado para ilustrar cómo se usa BAM para almacenar información de una aplicación que no es una orquestación de BizTalk. Aunque la aplicación es sencilla, ilustra diversos aspectos de BAM que es probable que use en una aplicación de producción. Entre ellas, figuran:  
  
-   Varios subprocesos que contribuyen a una sola actividad  
  
-   Creación de una relación entre dos actividades  
  
-   Uso de una continuación para permitir que se pueda obtener acceso a la misma actividad con diferentes identificadores  
  
 El ejemplo de API de BAM consta de tres clases principales: uno para procesar la compra ordena, una para procesar envíos y otra para procesar facturas. Cada clase tiene un **RunOnce** método que recupera un mensaje de una cola y, a continuación, procesa el mensaje. Cada clase tiene también una **ejecutar** método que continuamente llama el **RunOnce** método.  
  
 El **RunOnce** método de la **PoApplication** clase hace lo siguiente:  
  
1.  Crea un mensaje XML que representa un pedido de compra.  
  
2.  Comienza una actividad BAMApiPo y se agrega a la información de actividad acerca del pedido de compra y cuándo se recibió.  
  
3.  Aprueba arbitrariamente o rechaza el pedido de compra.  
  
4.  Actualiza la actividad BAMApiPo para registrar el estado del pedido de compra (aceptado o rechazado).  
  
5.  Si se aceptó el pedido de compra, la **RunOnce** método también hace lo siguiente:  
  
    1.  Crea un mensaje XML para representar un paquete que se va a enviar y agrega el mensaje a la cola de envíos.  
  
    2.  Agrega el mensaje XML que representa el pedido de compra a la cola de pedidos de compra que se van a incluir en una factura.  
  
    3.  Permite la continuación de la actividad BAMApiPo.  
  
    4.  Finaliza la actividad BAMApiPo.  
  
 El **RunOnce** método de la **ShipmentApplication** clase hace lo siguiente:  
  
1.  Recupera de su cola un mensaje XML que representa un paquete que se van a enviar.  
  
2.  Actualiza la actividad BAMApiPo para registrar la hora en la que se envió el paquete.  
  
3.  Finaliza la actividad BAMApiPo.  
  
 El **RunOnce** método de la **InvoiceApplication** clase hace lo siguiente:  
  
1.  Recupera de su cola un mensaje XML que representa un pedido de compra que se va a facturar.  
  
2.  Comienza una actividad BAMApiInvoice.  
  
3.  Crea una relación BAM entre la actividad BAMApiInvoice y la actividad BAMApiPo para el pedido de compra que se va a facturar.  
  
4.  Agrega a la actividad BAMApiPo información acerca de la factura y su hora de creación.  
  
5.  Después de un retraso arbitrario para simular la espera a que se abone la factura, agrega a la actividad BAMApiInvoice la hora en que se pagó la factura.  
  
6.  Finaliza la actividad BAMApiInvoice.  
  
 El **Main** método de la **MainApp** clase inicializa la aplicación. Realiza las operaciones siguientes:  
  
1.  Crea un **DirectEventStream** objeto.  
  
2.  Inicia varios subprocesos y llama a la **ejecutar** método de la **POApplication** objeto en cada subproceso.  
  
3.  Inicia varios subprocesos y llama a la **ejecutar** método de la **ShipmentApplication** objeto en cada subproceso.  
  
4.  Inicia varios subprocesos y llama a la **ejecutar** método de la **InvoiceApplication** objeto en cada subproceso.  
  
 El **Global** clase define las constantes que se usan por la aplicación de ejemplo, como el número de subprocesos para crear y el porcentaje de los pedidos de compra para rechazar.  
  
 Además de la solución [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], el ejemplo también contiene un archivo Microsoft [!INCLUDE[btsExcel](../includes/btsexcel-md.md)] que define las actividades.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Puede encontrar este ejemplo en  *\<ruta de ejemplos\>*\BAM\BamApiSample.  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivo|Description|  
|----------|-----------------|  
|BamApiSample.cs|Aplicación instrumentada.|  
|BamApiSample.csproj|Proyecto de aplicación instrumentada.|  
|BamApiSample.sln|Solución de aplicación instrumentada.|  
|BamApiSample.xls|Hoja de estilos de definición de BAM.|  
|Cleanup.bat|Archivo por lotes para quitar archivos de ejemplo implementados.|  
|Input.txt|Entrada de configuración del interceptor de ejemplo.|  
|InterceptorConfig.cs|Código de configuración de interceptor del ejemplo de API.|  
|InterceptorConfig.csproj|Proyecto de configuración de interceptor.|  
|Invoice_config.xml|Configuración del interceptor de facturación.|  
|Invoice_interceptor.bin|Interceptor de facturación serializado.|  
|PurchaseOrder_config.xml|Configuración del interceptor PurchaseOrder.|  
|PurchaseOrder_interceptor.bin|Interceptor PurchaseOrder serializado.|  
|Setup.bat|Archivo por lotes para implementar y dar de alta archivos de ejemplo.|  
|Shipment_config.xml|Configuración del interceptor de envío.|  
|Shipment_interceptor.bin|Interceptor de envío serializado.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Use el procedimiento siguiente para ejecutar la API de BAM de ejemplo y ver los resultados.  
  
#### <a name="to-run-the-bam-api-sample"></a>Procedimiento para ejecutar el ejemplo de API de BAM  
  
1.  Abra un símbolo del sistema y ejecute  *\<ruta de ejemplos\>*\BAM\ BamApiSample\setup.bat. Si usa [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], abra el símbolo del sistema como administrador.  
  
2.  Iniciar [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]y abra el  *\<ruta de ejemplos\>*solución \bam\. Si está usando [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], inicie [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] como administrador.  
  
    > [!IMPORTANT]
    >  La línea `//#define Interceptor` del archivo BamApiSample.cs debe marcarse como comentario. No quite el signo “//” desde esta línea. El ejemplo de API de BAM usa solo el código que no se encuentra dentro de una directiva de preprocesador `#if Interceptor`.  
  
3.  Compile la solución.  
  
4.  Ejecutar  *\<ejemplos de ruta de acceso\>*\BAM\BamApiSample\bin\debug\BamApiSample.exe.  
  
     El resultado será similar al siguiente:  
  
    ```  
    ...  
    New Purchase Order #17 Received  
    8 was shipped as pkg#87  
    New Purchase Order #18 Received.  
    Shipping package pkg#87 via DHL  
    13 was Approved.  
    18 was Rejected.  
    17 was Rejected.  
    11 was shipped as pkg#114  
    16 wsas Rejected.  
    Shipping package pkg#114 via DHL  
    Invoice #5 send for {2 5 1 9 4 8 11 }  
    Package pkg#49 was delivered  
    New Purchase Order #19 Received.  
    ...  
    ```  
  
5.  Al cabo de un minuto aproximadamente, presione CTRL+C o cierre la ventana del símbolo del sistema para detener el programa BamApiSample.  
  
#### <a name="to-view-the-results-of-running-the-bam-api-sample"></a>Procedimiento para ver los resultados de ejecutar el ejemplo de API de BAM  
  
1.  Abra SQL Server Management Studio.  
  
2.  En SQL Server Management Studio, expanda el servidor, expanda **bases de datos**, expanda **BAMPrimaryImport**y, a continuación, expanda **tablas**.  
  
3.  Haga clic en **dbo.bam_BAMApiInvoice_Active** y, a continuación, haga clic en **Abrir tabla**. Si está utilizando SQL Server, haga clic en **seleccionar las primeras 1000 filas**.  
  
     El contenido de la tabla bam_BAMApiInvoice_Active se muestra en el panel derecho. Cada fila de la tabla representa una actividad BAMApiInvoice que se ha iniciado, pero que no se ha completado.  
  
4.  Haga clic en **dbo.bam_BAMApiPo_Completed** y, a continuación, haga clic en **Abrir tabla**. Si está utilizando SQL Server, haga clic en **seleccionar las primeras 1000 filas**.  
  
     El contenido de la tabla bam_BAMApiPo_Completed se muestra en el panel derecho. Cada fila de la tabla representa una actividad BAMApiPo que se ha completado.