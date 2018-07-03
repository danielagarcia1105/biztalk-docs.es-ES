---
title: Clases EventStream | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3e7a6b3-69cc-4312-9074-acccd1175d37
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c4cb000d479a51d2215bda6349adfa6df39338a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973565"
---
# <a name="eventstream-classes"></a>Clases EventStream
Las API EventStream de BAM residen en el espacio de nombres Microsoft.BizTalk.BAM.EventObservation. Para escribir código basado en las API, deberá instalar primero los siguientes DLL en el equipo de desarrollo:  
  
- Microsoft.BizTalk.BAM.EventObservation.dll  
  
- Microsoft.Biztalk.BAM.Xlangs.dll: Este archivo DLL se requiere cuando se codifica para secuencias de eventos de orquestación.  
  
- Microsoft.BizTalk.Pipeline.dll: Este archivo DLL necesario al usar contextos de canalizaciones de codificación para secuencias de eventos de mensajería.  
  
  Agregue el DLL al proyecto de referencia e incluya el espacio de nombres en el código con la siguiente instrucción de uso:  
  
```  
using Microsoft.BizTalk.Bam.EventObservation;  
```  
  
 **Clases**  
  
|Nombre|Descripción|  
|----------|-----------------|  
|DirectEventStream (DES)|Sincrónico, sin latencia|  
|BufferedEventStream (BES)|Asíncrono, alto rendimiento, alguna latencia|  
|OrchestrationEventStream (OES)|Asíncrono, participa en transacciones de orquestaciones de BizTalk|  
|IPipelineContext (interfaz)|Asíncrono, participa en transacciones de canalización de BizTalk Server. Usado para crear secuencias de eventos de mensajería (MES).|  
  
 Debería elegir una API según los siguientes factores:  
  
- Si lo que le interesa es la latencia, elija DES, donde los datos persisten sincrónicamente en la base de datos de importación principal de BAM. Excepto DES, todas las demás clases EventStream son asincrónicas y tienen alguna latencia. Primero se conservan los datos en MessageBox y posteriormente TDDS los procesa y los mueve a la base de datos BAMPrimaryImport.  
  
- Si lo que le interesa es el rendimiento y la producción de inserción de eventos, elija una API asíncrona.  
  
- Si está escribiendo una aplicación que se ejecuta en un equipo que no tiene BizTalk Server instalado, use DES y BES. (Dicho de otro modo, estas API pueden usarse en aplicaciones que no sean de BizTalk).  
  
- Si la aplicación se ejecuta en un equipo que tiene BizTalk Server instalado, use MES y OES. (Estas API están disponibles únicamente desde aplicaciones de BizTalk).  
  
  -   Si quiere que la persistencia de eventos de BAM esté sincronizada con la transacción de canalización, deberá usar una secuencia de eventos de mensajería.  
  
  -   OES es el equivalente de MES pero para orquestaciones de BizTalk.  
  
  Existen escenarios en los que quizá desee mezclar tipos EventStream: Por ejemplo, en un procesamiento de canalización puede que desee capturar los datos específicos de BAM independientemente de si la canalización está revirtiendo la transacción o no. Concretamente, puede que desee capturar datos sobre cuántos mensajes produjeron un error o cuántos reintentos hubo durante el procesamiento de canalización. Para capturar datos en esta situación, debe usar BES.  
  
  Todas las EventStreams (BES, MES y OES) asíncronas almacenan primero los datos en la base de datos de cuadro de mensajes de BizTalk. De forma periódica, el Servicio de descodificación de datos de seguimiento (TDDS) los datos se procesan y se almacenan de forma permanente en la base de datos de importación principal de BAM.  
  
> [!NOTE]
>  Para asegurarse de que las llamadas de EventStream no crean un cuello de botella desde una aplicación de BizTalk, es recomendable que use API asíncronas.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [OrchestrationEventStream](../core/orchestrationeventstream.md)  
  
-   [Secuencias de eventos de mensajería](../core/messaging-event-streams.md)