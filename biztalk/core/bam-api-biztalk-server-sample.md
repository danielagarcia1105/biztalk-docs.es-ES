---
title: Ejemplo de API de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32a925f2-c7f4-4111-9c59-8865f15c6a89
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 899b28a95b6f07d7aec20868ea6b71138acfe60f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987381"
---
# <a name="bam-api-biztalk-server-sample"></a>API de BAM (ejemplo de BizTalk Server)
El ejemplo de API de BAM ilustra el modo de incorporar llamadas a la API de BAM en una aplicación para guardar información de claves que podrá supervisar.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En este ejemplo se implementa un escenario simple de compra. Genera pedidos de compra, procesa cada pedido de compra, crea envíos y crea y procesa facturas. Según se ejecuta el ejemplo, crea y actualiza actividades BAM para reflejar los detalles y la disposición de los pedidos de compra y facturas.  
  
## <a name="how-this-sample-was-designed-and-why"></a>Cómo y por qué se ha diseñado este ejemplo  
 Este ejemplo se ha diseñado para ilustrar cómo se usa BAM para almacenar información de una aplicación que no es una orquestación de BizTalk. Aunque la aplicación es sencilla, ilustra diversos aspectos de BAM que es probable que use en una aplicación de producción. Entre ellas, figuran:  
  
- Varios subprocesos que contribuyen a una sola actividad  
  
- Creación de una relación entre dos actividades  
  
- Uso de una continuación para permitir que se pueda obtener acceso a la misma actividad con diferentes identificadores  
  
  El ejemplo de API de BAM consta de tres clases principales: uno para procesar la compra de pedidos, uno para procesar envíos y otro para procesar facturas. Cada clase tiene un **RunOnce** método que recupera un mensaje de una cola y, a continuación, procesa el mensaje. Cada clase tiene también un **ejecutar** método que continuamente llama el **RunOnce** método.  
  
  El **RunOnce** método de la **PoApplication** clase hace lo siguiente:  
  
1. Crea un mensaje XML que representa un pedido de compra.  
  
2. Comienza una actividad BAMApiPo y se agrega a la información de actividad acerca del pedido de compra y cuándo se recibió.  
  
3. Aprueba arbitrariamente o rechaza el pedido de compra.  
  
4. Actualiza la actividad BAMApiPo para registrar el estado del pedido de compra (aceptado o rechazado).  
  
5. Si se aceptó el pedido de compra, el **RunOnce** método también hace lo siguiente:  
  
   1.  Crea un mensaje XML para representar un paquete que se va a enviar y agrega el mensaje a la cola de envíos.  
  
   2.  Agrega el mensaje XML que representa el pedido de compra a la cola de pedidos de compra que se van a incluir en una factura.  
  
   3.  Permite la continuación de la actividad BAMApiPo.  
  
   4.  Finaliza la actividad BAMApiPo.  
  
   El **RunOnce** método de la **ShipmentApplication** clase hace lo siguiente:  
  
6. Recupera de su cola un mensaje XML que representa un paquete que se van a enviar.  
  
7. Actualiza la actividad BAMApiPo para registrar la hora en la que se envió el paquete.  
  
8. Finaliza la actividad BAMApiPo.  
  
   El **RunOnce** método de la **InvoiceApplication** clase hace lo siguiente:  
  
9. Recupera de su cola un mensaje XML que representa un pedido de compra que se va a facturar.  
  
10. Comienza una actividad BAMApiInvoice.  
  
11. Crea una relación BAM entre la actividad BAMApiInvoice y la actividad BAMApiPo para el pedido de compra que se va a facturar.  
  
12. Agrega a la actividad BAMApiPo información acerca de la factura y su hora de creación.  
  
13. Después de un retraso arbitrario para simular la espera a que se abone la factura, agrega a la actividad BAMApiInvoice la hora en que se pagó la factura.  
  
14. Finaliza la actividad BAMApiInvoice.  
  
    El **Main** método de la **MainApp** clase inicializa la aplicación. Realiza las operaciones siguientes:  
  
15. Crea un **DirectEventStream** objeto.  
  
16. Inicia varios subprocesos y llama a la **ejecutar** método de la **POApplication** objeto en cada subproceso.  
  
17. Inicia varios subprocesos y llama a la **ejecutar** método de la **ShipmentApplication** objeto en cada subproceso.  
  
18. Inicia varios subprocesos y llama a la **ejecutar** método de la **InvoiceApplication** objeto en cada subproceso.  
  
    El **Global** clase define las constantes que se usan por la aplicación de ejemplo, como el número de subprocesos para crear y el porcentaje de pedidos de compra a rechazar.  
  
    Además de la solución de Visual Studio, el ejemplo también contiene un archivo de Microsoft Excel que define las actividades.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Puede encontrar este ejemplo en  *\<ruta de ejemplos\>* \BAM\BamApiSample.  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivo|Descripción|  
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
  
## <a name="run-the-bam-api-sample"></a>Ejecutar el ejemplo de API de BAM  
  
1.  Abra un símbolo del sistema como administrador y ejecute  *\<ruta de ejemplos\>* \BAM\ BamApiSample\setup.bat.  
  
2.  Inicie Visual Studio como administrador y abra el  *\<ruta de ejemplos\>* \BAM\ BamApiSample\BamApiSample.sln solución. 
  
    > [!IMPORTANT]
    >  La línea `//#define Interceptor` del archivo BamApiSample.cs debe marcarse como comentario. No quite el signo “//” desde esta línea. El ejemplo de API de BAM usa solo el código que no se encuentra dentro de una directiva de preprocesador `#if Interceptor`.  
  
3.  Compile la solución.  
  
4.  Ejecute  *\<ejemplos de la ruta de acceso\>* \BAM\BamApiSample\bin\debug\BamApiSample.exe.  
  
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
  
## <a name="view-the-results"></a>Ver los resultados
  
1.  Abra SQL Server Management Studio.  
  
2.  En SQL Server Management Studio, expanda el servidor, **bases de datos**, expanda **BAMPrimaryImport**y, a continuación, expanda **tablas**.  
  
3.  Haga clic en **dbo.bam_BAMApiInvoice_Active** y, a continuación, haga clic en **Abrir tabla**. Si usa SQL Server, haga clic en **seleccionar las 1000 primeras filas**.  
  
     El contenido de la tabla bam_BAMApiInvoice_Active se muestra en el panel derecho. Cada fila de la tabla representa una actividad BAMApiInvoice que se ha iniciado, pero que no se ha completado.  
  
4.  Haga clic en **dbo.bam_BAMApiPo_Completed** y, a continuación, haga clic en **Abrir tabla**. Si usa SQL Server, haga clic en **seleccionar las 1000 primeras filas**.  
  
     El contenido de la tabla bam_BAMApiPo_Completed se muestra en el panel derecho. Cada fila de la tabla representa una actividad BAMApiPo que se ha completado.