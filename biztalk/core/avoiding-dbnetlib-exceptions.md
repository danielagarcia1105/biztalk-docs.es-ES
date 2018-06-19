---
title: Evitar excepciones DBNETLIB | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fbee0cf-d249-4d98-8d16-168ded32f9f1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decd258c5f4c965c79d9821c82671c6997ac9e3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231916"
---
# <a name="avoiding-dbnetlib-exceptions"></a>Evitar excepciones DBNETLIB
Se producen errores de DBNetLib (Biblioteca de red de bases de datos) cuando el tiempo de ejecución de BizTalk Server no se puede comunicar con las bases de datos de cuadro de mensajes o de administración. Cuando esto sucede, la instancia de BizTalk Server en tiempo de ejecución que detecta la excepción se apaga y a continuación, se desplaza cada minuto para comprobar si la base de datos está disponible.  
  
 La causa más común de un error de DBNetLib es cuando uno de los (posiblemente muchos) servidores de bases de datos de cuadros de mensajes está muy ocupado y los repetidos intentos para establecer comunicación dan como resultado un tiempo de espera que provoca una excepción de DBNetLib.  
  
 Además del caso en el que la base de datos de cuadro de mensajes simplemente está muy ocupada, el error de DBNetLib puede producirse en un entorno de producción cuando servidores de bases de datos de BizTalk que hospedan una o varias bases de datos de cuadro de mensajes se enlazan en las E/S (Entradas/Salidas).  
  
 En este tema se describen las condiciones que pueden conducir a errores DBNetLib y las recomendaciones para evitar que se produzcan.  
  
## <a name="cause-and-resolution-for-the-dbnetlib-error"></a>Causa y solución para el error de DBNetLib  
  
### <a name="symptoms-of-a-dbnetlib-error"></a>Síntomas de un error de DBNetLib  
 Una instancia de host de Microsoft BizTalk Server finaliza, se reinicia y se escriben errores similares a los que se incluyen a continuación en el registro de aplicaciones de BizTalk Server:  
  
```  
Event Type:Warning  
Event Source:BizTalk Server <version>  
Event Category:BizTalk Server <version>   
Event ID:5410  
Computer:BIZTALKSERVER  
Description:  
An error occurred that requires the BizTalk service to terminate. The most common causes are the following:  
 1) An unexpected out of memory error.  
 OR  
 2) An inability to connect or a loss of connectivity to one of the BizTalk databases.   
 The service will shutdown and auto-restart in 1 minute. If the problematic database remains unavailable, this cycle will repeat.  
  
 Error message: [DBNETLIB][ConnectionWrite (send()).]General network error. Check your network documentation.  
 Error source:    
  
 BizTalk host name: BizTalkHost  
 Windows service name: BTSSvc$BizTalkHost   
  
---------------------------------------------------------  
Event Type:Error  
Event Source:BizTalk Server <version>  
Event Category:BizTalk Server <version>   
Event ID:6913  
Computer:BIZTALKSERVER  
Description:  
An attempt to connect to "BizTalkMsgBoxDb" SQL Server database on server "SQLSERVER " failed.  
 Error: "[DBNETLIB][ConnectionWrite (send()).]General network error. Check your network documentation."  
```  
  
### <a name="biztalk-database-servers-hosting-messagebox-databases-becoming-io-bound"></a>Enlace de E/S de servidores de bases de datos de BizTalk que alojan bases de datos de cuadros de mensajes  
 Los servidores de BizTalk se comunican y actúan directamente con los servidores de bases de datos que alojan bases de datos de cuadros de mensajes. Si cualquiera de los servidores de bases de datos que alojan las bases de datos de cuadros de mensajes se consume demasiado y entra en una situación de enlace de E/S (Entrada/Salida), es posible que no responda. Uno de los servidores de BizTalk podría perder la conectividad con uno de aquellos servidores de bases de datos, y producirse un error de DBNetLib.  
  
 Nuestras pruebas muestran que las E/S de un servidor de bases de datos muy consumido se enlazan cuando el valor "% de tiempo de inactividad" de su disco físico continúa cayendo por debajo del 10 %. Si el valor “% de tiempo de inactividad” continúa cayendo por debajo de ese nivel, es muy probable que el servidor de bases de datos deje de responder.  
  
#### <a name="cause"></a>Causa  
 Hay varias razones que pueden provocar que las entradas de E/S de los servidores de base de datos que alojan las bases de datos de cuadros de mensajes se enlacen, como por ejemplo:  
  
-   Si el equipo de base de datos que hospeda la base de datos de cuadro de mensajes tiene especificaciones de hardware insuficientes como: poca memoria, número y velocidad de procesadores reducidos, etc.  
  
-   Si el disco físico del equipo de base de datos que aloja una base de datos de cuadros de mensajes está siendo compartido por otras bases de datos muy consumidas. En casos en los que varias bases de datos, incluido el cuadro de mensajes, se están consumiendo al mismo tiempo, las E/S del disco físico pueden enlazarse.  
  
     A continuación, se incluye un ejemplo de esa situación:  
  
     Nuestras pruebas muestran que el servidor de bases de datos que aloja las bases de datos de BizTalkDTADb o BAM suele consumir altos porcentajes de los %Tiempos de lectura y escritura de disco de un disco físico. Cuando el disco del servidor de bases de datos que aloja una base de datos de cuadros de mensajes está siendo compartido por otra base de datos muy consumida, como BizTalkDTADb o BAM, y si las dos bases de datos se consumen al mismo tiempo, puede suceder que las E/S del disco físico del servidor de bases de datos se enlacen y dejen de responder.  
  
-   Si BizTalkDTADb y una o más bases de datos de cuadros de mensajes están compartiendo el mismo disco físico en el servidor de bases de datos y los procesos de archivado y purga no se están ejecutando con frecuencia, las E/S del disco pueden enlazarse.  
  
#### <a name="resolution"></a>Solución  
 Asegúrese de que el servidor de bases de datos que hospeda el cuadro de mensajes de BizTalk no llegue nunca a una situación de alto consumo que pueda provocar que deje de responder.  
  
 A continuación, se indican algunas de las causas principales por las que el disco de un servidor puede verse muy consumido, junto con recomendaciones para mitigar este problema.  
  
##### <a name="low-hardware-specs"></a>Especificaciones de hardware bajas  
 Nuestras pruebas muestran que el servidor comienza a consumirse más cuando las especificaciones de hardware no se actualizan al mismo ritmo que la carga que está intentando procesar. Cuanto más bajas sean las especificaciones de hardware, el sistema se sobrecarga con más rapidez por la cantidad de actividades que se producen en las bases de datos. Esto podría provocar que los %Tiempos de lectura y escritura de disco del servidor siguieran aumentando sin llegar a estabilizarse y el %de tiempo de inactividad siguiera descendiendo y llegara a ser inferior al 10%, por lo que podría provocar que el servidor de bases de datos dejara de responder.  
  
 En función de la cantidad de actividades y la carga de la implementación de BizTalk, si detecta que los servidores de bases de datos dejan de responder con las cargas altas, debería considerar la posibilidad de actualizar las piezas de los servidores de bases de datos que se indican a continuación: número de CPU, memoria y conexión con un SAN. Por supuesto, debería recibir el diagnóstico adecuado para calcular qué parte (memoria, número de CPU etc.) es el cuello de botella que necesita actualizarse en su hardware.  
  
##### <a name="sharing-one-server-or-disk-for-more-than-one-group-of-biztalk-databases"></a>Compartir un servidor o disco para más de un grupo de bases de datos de BizTalk  
 Como se ha mencionado anteriormente, las bases de datos que no sean las de cuadros de mensajes, como la base de datos de seguimiento de BizTalk (BizTalkDTADb) y las bases de datos de BAM podrían consumir altos ciclos en el disco físico de un servidor. Por tanto, si dichas bases de datos comparten el mismo disco físico con las bases de datos de cuadros de mensajes, podrían saturar el disco y hacer que dejara de responder, lo que podría provocar de nuevo que los servidores BizTalk Server perdieran la conectividad con las bases de datos de cuadro de mensajes y se produjeran errores DBNetLib.  
  
 Si esto se produce, recomendamos que separe las bases de datos que espera que tengan más consumo del disco físico del servidor desde el cuadro de mensajes de BizTalk, de modo que compartan discos físicos distintos (o separarlas en servidores distintos). Se recomienda colocar las bases de datos de BizTalkDTADb y BAM en unidades/servidores distintos desde el cuadro de mensajes; además, se recomienda tener cada base de datos de cuadros de mensajes (en el caso de que haya más de una) en su propio disco.  
  
##### <a name="archiving-and-purging"></a>Archivar y purgar  
 Si las bases de datos de BizTalkDTADb y cuadros de mensajes comparten el mismo disco en el mismo servidor, deberá archivar y purgar las bases de datos de BizTalkDTADb con regularidad; de lo contrario aumentarán de tamaño indefinidamente.  
  
 Las pruebas indican que resulta una práctica recomendable archivar y purgar las bases de datos con regularidad, pero que si se producen cargas más altas de lo normal, debería considerar la posibilidad de llevar a cabo los procesos de archivado y purga con más frecuencia. Si no se realiza un mantenimiento del crecimiento de las bases de datos de BizTalkDTADb, cuando se produzcan estas situaciones, es posible que le lleve más tiempo y consuma más recursos de los disponibles en el servidor de bases de datos mientras se ejecutan.