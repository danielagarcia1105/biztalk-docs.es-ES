---
title: Optimización de la actividad económica (BAM) rendimiento de supervisión | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9ed29b2-0be6-4a37-be68-9476832fd49f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f28771f2611a8b5f7c2522b7cd45e875897645e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996205"
---
# <a name="optimizing-business-activity-monitoring-bam-performance"></a>Optimización de la actividad económica (BAM) rendimiento de supervisión
En este tema se describe los factores de rendimiento de supervisión de la actividad económica (BAM).  
  
## <a name="bam-disk-usage-configuration"></a>Configuración de uso de disco BAM  
 BAM supone una sobrecarga considerable cuando un sistema de BizTalk está bajo carga debido a la importante cantidad de datos que se conservan en la base de datos BAM. Por lo tanto, juiciosamente uso de técnicas de E/S de disco para la base de datos BAM es muy importante.  
  
## <a name="bam-eventstream-apis"></a>API EventStream BAM  
 Cuatro tipos de EventStreams están disponibles para su uso en un escenario de BAM de BizTalk:  
  
- DirectEventStream (DES)  
  
- BufferedEventStream (BES)  
  
- OrchestrationEventStream (OES)  
  
- MessageEventStream (MES)  
  
  Debe elegir una de estas API según los factores siguientes:  
  
- Si lo que le interesa es la latencia, elija DES, donde los datos persisten sincrónicamente en la base de datos de importación principal de BAM.  
  
- Si le interesa es el rendimiento y el rendimiento de inserción de eventos, elija una API asíncrona (BES, OES o MES).  
  
- Si está escribiendo una aplicación que se ejecuta en un equipo que no tiene instalado BizTalk Server, use DES y BES; Estas API pueden usarse en aplicaciones que no sean de BizTalk.  
  
  > [!NOTE]  
  >  Existen escenarios en los que quizá desee mezclar tipos EventStream: Por ejemplo, para el procesamiento de canalización, puede capturar los datos específicos de BAM independientemente de si la canalización está revirtiendo la transacción. En concreto, puede que desee capturar datos sobre cuántos mensajes de error o cuántos reintentos se produjeron durante el procesamiento de canalización. Para capturar datos en esta situación, debe usar BES.  
  
- Si la aplicación se ejecuta en un equipo que tiene BizTalk Server instalado, use MES y OES. (Estas API están disponibles únicamente desde aplicaciones de BizTalk).  
  
  > [!NOTE]  
  >  OES es el equivalente de MES pero para orquestaciones de BizTalk.  
  
- Si desea que la persistencia de eventos BAM esté sincronizada con la transacción de canalización, debe usar un Stream de eventos de mensajería (MES).  
  
  Todas las EventStreams asincrónicas (BES, MES y OES) conservar los datos primero a la base de datos de BizTalk MessageBox. De forma periódica, el Servicio de descodificación de datos de seguimiento (TDDS) los datos se procesan y se almacenan de forma permanente en la base de datos de importación principal de BAM.  
  
  Para obtener más información sobre las BAM EventStream APIs, consulte [clases EventStream](http://go.microsoft.com/fwlink/?LinkId=158046) (http://go.microsoft.com/fwlink/?LinkId=158046) en la documentación de BizTalk Server.  
  
## <a name="bam-performance-counters"></a>Contadores de rendimiento de BAM  
 Para obtener una lista detallada de los contadores de rendimiento de BAM, consulte [contadores de rendimiento BAM](http://go.microsoft.com/fwlink/?LinkId=158048) (http://go.microsoft.com/fwlink/?LinkId=158048) en la documentación de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Optimización del rendimiento de BizTalk Server](../technical-guides/optimizing-biztalk-server-performance.md)