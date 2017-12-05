---
title: Agregador (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- pipelines, examples
- orchestrations, messages
- examples, pipelines
- messages, correlating to orchestrations
ms.assetid: eb8121df-4f5b-4f36-8228-4b5ad1abfb4e
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 493f4d28214a815aca88f214e5efb9cd883e7192
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="aggregator-biztalk-server-sample"></a>Agregación (ejemplo de BizTalk Server)
La finalidad de este ejemplo consiste en crear una funcionalidad de agregación de mensaje con orquestaciones y canalizaciones. De forma más específica, crearemos una orquestación que:  
  
1.  Recibe un conjunto de mensajes correlacionados. Los mensajes se correlacionan según la información de URI del socio comercial de destino que se extrae del contenido del mensaje.  
  
2.  Agrega los mensajes recibidos en un lote de intercambio único mediante la ejecución de una canalización de envío de XML.  
  
3.  Produce un mensaje de intercambio de XML cada minuto o en cuanto tiene suficientes mensajes para agregar.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso\>*\Pipelines\Aggregator  
  
 En la tabla siguiente se enumeran los archivos que se usan en el ejemplo.  
  
|Archivos|Description|  
|---------------|-----------------|  
|Aggregator.sln|Archivo de solución de Visual Studio para el ejemplo.|  
|AggretatorBinding.xml|Archivo de enlace para el ejemplo.|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC). Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
|En la carpeta Aggregate:<br /><br /> Aggregate.btproj|Proyecto de BizTalk para la orquestación de agregación.|  
|En la carpeta Aggregator:<br /><br /> Aggregate.odx|Orquestación que reúne los mensajes correlacionados y después ejecuta la canalización de envío para ensamblarlos en un intercambio único.|  
|En la carpeta Aggregate:<br /><br /> SuspendMessage.odx|Orquestación usada para suspender mensajes que no se pueden procesar en la orquestación de agregación.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> FFReceivePipeline.btp|Canalización de recepción con desensamblador de archivos sin formato.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> Instance1.txt, Instance2.txt, Instance3.txt, Instance4.txt|Instancias de documento para el ejemplo. Instance1.txt e Instance2.txt deben agregarse a un intercambio de socio comercial de destino [http://www.contoso.com](http://www.contoso.com/) mientras que Instance3.txt e Instance4.txt deben agregarse a un intercambio de socio comercial de destino [ http://www.Northwind.com](http://www.northwind.com/).|  
|En la carpeta PipelinesAndSchemas:<br /><br /> Invoice.xsd, InvoiceEnvelope.xsd|Esquema de documento y esquema de sobre para el intercambio de salida.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> PipelinesAndSchemas.btproj|Proyecto de BizTalk para los esquemas y las canalizaciones.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> PropertySchema.xsd|Esquema de propiedad del ejemplo.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> XMLAggregatingPipeline.btp|Canalización de envío que se ejecuta desde la orquestación para ensamblar mensajes recogidos en un intercambio de XML.|  
  
## <a name="building-and-initializing-the-sample"></a>Crear e inicializar el ejemplo  
 Utilice el siguiente procedimiento para crear e inicializar el ejemplo de agregación.  
  
#### <a name="to-build-and-initialize-the-aggregator-sample"></a>Para crear e inicializar el ejemplo de agregación  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<Ejemplos de ruta de acceso\>\Pipelines\Aggregator  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Crea las carpetas de entrada (In) y de salida (Out) de este ejemplo en la carpeta:  
  
         \<Ejemplos de ruta de acceso\>\Pipelines\Aggregator  
  
    -   Compila los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.  
  
    -   Crea una aplicación nueva llamada "Aggregator Sample" e implementa los ensamblados de ejemplo en ella.  
  
    -   Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.  
  
    -   Da de alta e inicia la orquestación, habilita la ubicación de recepción e inicia el puerto de envío.  
  
         Si opta por abrir y crear los proyectos en este ejemplo sin ejecutar el archivo Setup.bat, primero debe crear un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice que este par de claves se usa para firmar los ensamblados resultantes.  
  
3.  Antes de intentar ejecutar este ejemplo, confirme que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha notificado ningún error durante el proceso de compilación e inicialización.  
  
     Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="running-the-sample"></a>Ejecutar el ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo de agregación.  
  
#### <a name="to-run-the-aggregator-sample"></a>Para ejecutar el ejemplo de agregación  
  
1.  Abra los archivos Instance1.txt e Instance2.txt que se encuentran en la carpeta PipelinesAndSchemas para inspeccionar su contenido.  
  
     Tenga en cuenta que en ambos archivos, el elemento DestinationPartnerURI contiene el valor http://www.contoso.com. Este valor se usará para correlacionar estos dos mensajes juntos de modo que se puedan agregar a un intercambio.  
  
     Del mismo modo, los archivos Instance3.txt e Instance4.txt tienen el elemento DestinationPatnerURI establecido en http://www.northwind.com.  
  
     Estos dos mensajes juntos se agregarán a un intercambio diferente.  
  
2.  Pegue copias de los archivos de texto Instance1.txt, Instance2.txt, Instance3.txt e Instance4.txt en la carpeta In.  
  
3.  Las orquestaciones de agregación producen intercambios de salida en cuanto recogen 10 mensajes o cuando transcurre 1 minuto de tiempo de espera. Debido a eso, los archivos en la carpeta Out pueden aparecer con retraso.  
  
     Para evitar el tiempo de espera, puede pegar los cuatro archivos de entrada cuatro veces lo que desencadenaría que las orquestaciones de agregación produzcan los intercambios.  
  
4.  Observe los archivos XML creados en la carpeta Out. Debería haber dos archivos: uno por cada URI de socio comercial de destino.  
  
     Abra uno de los archivos para inspeccionar su contenido. El archivo debe contener un intercambio de XML que consista en un sobre y dos documentos XML dentro de él.  
  
    > [!NOTE]
    >  La implementación de ejemplo puede producir "mensajes entregados, no consumidos" o "Completado con mensajes descartados" con una carga elevado en un escenario de convoyes. Esto se produce cada vez que la ruta de un mensaje se dirige a un proceso empresarial que está en el proceso de finalización o cada vez que llegan mensajes inesperados a un proceso empresarial.  
  
## <a name="see-also"></a>Vea también  
 [Canalizaciones (carpeta de ejemplos de BizTalk Server)](../core/pipelines-biztalk-server-samples-folder.md)