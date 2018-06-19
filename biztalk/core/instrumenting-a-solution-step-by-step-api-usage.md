---
title: 'Instrumentar una solución: uso de la API de paso a paso | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9e027ab-1927-4905-8970-8061ac55d591
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73c59ab28c228c779fd9e6e84d836b87415d6386
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258236"
---
# <a name="instrumenting-a-solution-step-by-step-api-usage"></a>Instrumentar una solución: uso de la API de paso a paso
En este tema se describe cómo instrumentar una aplicación con la clase principal de la API de BAM. En los siguientes fragmentos de código hemos simplificado el código de ejemplo mediante el uso de constantes y con el código mínimo necesario para instrumentar una aplicación.  
  
 El siguiente fragmento de código demuestra cómo crear un objeto [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) nuevo; en concreto, un objeto [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx). En este fragmento, el primer parámetro especifica la cadena de conexión al almacén de datos de la base de datos de importación principal de BAM, y el segundo parámetro indica la frecuencia con la que se escriben los eventos en el almacén de datos.  
  
> [!NOTE]
>  BAM solo admite conexiones a almacenes de datos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. La cadena de conexión de ejemplo representa la cadena de conexión mínima necesaria para establecer una conexión. En su configuración, puede que sea necesario especificar parámetros adicionales en la cadena de conexión.  
  
 Un valor *FlushThreshold* de 0 indica que los eventos no se escriben automáticamente y que es preciso llamar al método Flush para escribir los eventos. Un valor de 1 hace que los eventos se escriban en el momento de generarse. Los valores mayores que 1 determinan que los eventos se escriben cuando se crea un lote de la acumulación especificada. Usar un valor mayor que 1 puede ser útil para mejorar el rendimiento.  
  
```  
// Specify the DES connection string.  
const string connBAMPIT =  
   "Integrated Security=SSPI;server=.;database=BAMPrimaryImport";  
// Write the activity update data on every call.  
int flushThreshold = 1;  
// Create a DES instance  
EventStream es =   
   new DirectEventStream(connBAMPIT, flushThreshold);  
```  
  
 Una vez creado el objeto [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) , puede comenzar la actividad e iniciar la actualización de la tabla de la actividad con los hitos y los datos recopilados. Cuando se implementó la actividad de BAM, se crearon cinco tablas en la base de datos de importación principal de BAM. Para obtener más información sobre el proceso de desarrollo, consulte [información general sobre el proceso de desarrollo de BAM](../core/overview-of-the-bam-development-process.md).  
  
 Al llamar al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) , se agrega un registro a la tabla bam_ PurchaseOrder_Activity. El primer parámetro contiene el nombre de la actividad que se está actualizando, y el segundo, un identificador para esta instancia de la actividad. El identificador puede ser cualquier cadena, pero debe ser único en el conjunto de registros de la actividad.  
  
 En este momento, el registro no contiene ningún dato. El método [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) actualiza el registro con los datos de los eventos capturados. Una vez más, debe especificar una actividad y el identificador de la instancia de la actividad. Pase los pares de nombre y valor de los elementos de datos e hitos que definió en la actividad para el método [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) . Por ejemplo, en nuestra actividad se definió un hito denominado MS_Received. Cuando se implementó la actividad, se creó una columna en la tabla bam_ PurchaseOrder_Activity para el hito. La llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) especifica que el par de nombre y valor MS_Received y DateTime.UtcNow actualicen la actividad con la fecha de recepción del pedido de compra.  
  
```  
// When a purchase order is received, you call the  
// BeginActivity method in the receive application.  
// You can then capture the event data by calling   
// the UpdateActivity method.  
es.BeginActivity ("PurchaseOrder", "PO123");  
es.UpdateActivity ("PurchaseOrder", "PO123",  
                    "MS_Received", DateTime.UtcNow,   
                    "T_Customer", "Joe");  
```  
  
 En este ejemplo, vamos a realizar una continuación en una segunda actividad. Para obtener más información acerca de las continuaciones, consulte [continuación de actividad](../core/activity-continuation.md).  
  
 Para permitir que otras aplicaciones instrumentadas actualicen la actividad PurchaseOrder, incluya una llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) . La llamada especifica la actividad a la que pueden contribuir otras aplicaciones, el identificador de la instancia de la actividad cuyo seguimiento se está realizando y el token de continuación que otras aplicaciones usarán para actualizar la actividad. Para realizar un seguimiento del estado de la continuación, se escribe un registro en la tabla bam_ PurchaseOrder_continuations. Si la actividad continúa en otros procesos, se escribe un registro para cada llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) con un token de continuación único.  
  
> [!IMPORTANT]
>  Cada segmento de código en un escenario de continuación debe tener su propia llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) . De lo contrario, se creará un registro de actividad suelto o huérfano.  
>   
>  Sin embargo, solo el primer segmento (que usa el identificador real de la actividad) tiene el método [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) ; todos los demás segmentos (que usan su propio identificador de token único) no deben llamar al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) .  
  
 Después de llamar al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) , otros componentes pueden actualizar la actividad de pedido de compra mediante [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) , especificando el token de continuación en lugar del identificador de la actividad. Cuando los demás componentes hayan completado sus tareas, todos ellos deben llamar a [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) con el token de continuación para informar a la infraestructura de BAM de que no se esperan más eventos.  
  
> [!IMPORTANT]
>  Una vez llamado el método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) , es posible que una actividad se quede huérfana si el proceso en el que continúa no llama nunca a un método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) con el token de continuación.  
  
```  
// Continue the activity to the next process that has been  
// instrumented to handle the continuation.  
es.EnableContinuation("PurchaseOrder", “PO123”, “AP123”);  
```  
  
 Por último, la actividad se finaliza con una llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) y la especificación del nombre e identificador de la actividad. Si no hay ninguna continuación sin finalizar, la actividad se mueve a la tabla bam_ PurchaseOrder _completed. Es posible que las actividades se queden huérfanas si no se pueden completar las actividades de continuación.  
  
```  
// Activity from this segment (PO submission) is completed  
es.EndActivity("PurchaseOrder", “PO123”);  
```  
  
 Cuando la actividad continúa en otro proceso, la aplicación se instrumenta para actualizar la tabla de la actividad mediante una llamada a [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) y la especificación del nombre de actividad y el token de continuación declarados en la llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) .  
  
> [!NOTE]
>  El proceso que controla la actividad continuada no llama al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) . El método [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) crea una instancia de la actividad mediante la creación de las tablas en la base de datos de importación principal de BAM. El proceso en el que continúa la actividad actualiza la instancia de la actividad ya existente.  
  
```  
// update when the order is approved  
es.UpdateActivity ("PurchaseOrder", “AP123”, "MS_Approved",  
                    DateTime.UtcNow, "T_Product", "Widget");  
  
// update when the product is ready for shipment  
es.UpdateActivity ("PurchaseOrder", “AP123”,  
                   "MS_Ready", DateTime.UtcNow);  
```  
  
 Parte del flujo de trabajo del código de este ejemplo especifica una referencia; en este caso, un tipo específico de referencia: una actividad relacionada. Al especificar una actividad relacionada, crea un vínculo desde la actividad principal a otras actividades que interesan a un usuario que ve la actividad en el portal de BAM.  
  
 La llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.AddRelatedActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.addrelatedactivity.aspx) escribe un registro enbam_ PurchaseOrder_ActiveRelationships que vincula las actividades.  
  
```  
// These are shipped in two shipments.  
// Relates the current purchase order   
// instance to two shippings.  
// Note: only one direction  
es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                       "Shipping", “UPS101”);  
es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                       "Shipping", “UPS102”);  
```  
  
 Para finalizar la actividad continuada, debe llamar al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) y especificar el token de continuación correspondiente a la continuación que está finalizando. Si no hay ninguna otra continuación sin finalizar, la actividad PurchaseOrder se mueve a la tabla _completed.  
  
```  
// Activity from this segment (ApprovalProcess) is completed  
es.EndActivity("PurchaseOrder", “AP123”);  
```  
  
## <a name="complete-code-sample"></a>Ejemplo con todo el código  
  
```  
//---------------------------------------------------------------------  
// File:BAMMinimalSample.cs  
//   
// Summary: Demonstrates how to instrument an application   
//using BAM APIs to track useful information.  
//  
// Sample: BAM Api Sample  
//  
//---------------------------------------------------------------------  
// This file is part of the Microsoft BizTalk Server SDK  
//  
// Copyright (c) Microsoft Corporation. All rights reserved.  
//  
// This source code is intended only as a supplement to Microsoft   
// BizTalk Server release and/or on-line documentation. See   
// these other materials for detailed information regarding Microsoft // code samples.  
//  
// THIS CODE AND INFORMATION ARE PROVIDED "AS IS" WITHOUT WARRANTY OF  
// ANY KIND, WHETHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO // THE IMPLIED WARRANTIES OF MERCHANTABILITY AND/OR FITNESS FOR A   
// PARTICULAR PURPOSE.  
//---------------------------------------------------------------------  
// This sample requires that you add the     
// Microsoft.BizTalk.Bam.EventObservation.dll to the   
// references in the Visual Studio Solution.  
  
using System;  
using System.Text;  
using Microsoft.BizTalk.Bam.EventObservation;  
  
namespace EventStreamSample  
{  
  
    static void Main(string[] args)  
    {  
        //   
  // The following code would appear in a purchase order  
   // receipt application.  
        //  
  
        // Specify the DES connection string.  
        const string connBAMPIT =  
            "Integrated Security=SSPI;server=.;database=BAMPrimaryImport";  
  
        // Write the activity update data on every call.  
        int flushThreshold = 1;  
  
        // Create an instance of the DirectEventStream.  
        EventStream es =   
               new DirectEventStream(connBAMPIT, flushThreshold);  
  
        // When a purchase order is received, you call the  
       // BeginActivity method in the receive application.  
  // You can then capture the event data by calling   
        // the UpdateActivity method.  
        es.BeginActivity ("PurchaseOrder", "PO123");  
        es.UpdateActivity ("PurchaseOrder", "PO123",  
                    "MS_Received", DateTime.UtcNow,   
                    "T_Customer", "Joe");  
  
   // Continue the activity to the next process that has been  
   // instrumented to handle the continuation.  
        es.EnableContinuation("PurchaseOrder", “PO123”, “AP123”);  
  
        // Activity from this segment (PO submission) is completed  
        // end activity is synonymous to IsCompleted = 1  
        es.EndActivity("PurchaseOrder", “PO123”);  
  
        //  
        // The following code would typically appear in a separate   
        // application that monitors the approval process  
        // (ApprovalProcess.exe)  
        //  
  
        // update when the order is approved  
        es.UpdateActivity ("PurchaseOrder", “AP123”, "MS_Approved",  
                            DateTime.UtcNow, "T_Product", "Widget");  
  
        // update when the product is ready for shipment  
        es.UpdateActivity ("PurchaseOrder", “AP123”,  
                            "MS_Ready", DateTime.UtcNow);  
  
        // These are shipped in two shipments.  
        // Relates the current purchase order  
        // instance to two shippings.  
        // Note: only one direction  
        es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                                "Shipping", “UPS101”);  
        es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                                "Shipping", “UPS102”);  
  
        // Activity from this segment (ApprovalProcess) is completed  
        es.EndActivity("PurchaseOrder", “AP123”);  
  
        // In another Shipping application, two shipments with  
            ID’s UPS101 and UPS102 will be created.  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Implementar actividades BAM con secuencias de eventos](../core/implementing-bam-activities-with-event-streams.md)