---
title: Comprender el comportamiento del rendimiento del seguimiento DTA | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1a70951-bfed-435c-97f4-0b28a8e4e4dc
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 278d1e3c4b52c14c68d692ce3d3a3179d15bb10b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="understanding-dta-tracking-performance-behavior"></a>Comprender el comportamiento del rendimiento de seguimiento de DTA
Los factores principales que determinan el rendimiento máximo sostenible (MST) para el seguimiento de DTA son:  
  
-   El rendimiento de mensajes deseado, es decir, los mensajes recibidos por unidad de tiempo para el sistema.  
  
-   Cantidad de datos a los que se realiza el seguimiento para cada mensaje.  
  
-   Tiempo de vida de los datos en la base de datos de BizTalkDTADb antes de que se purguen, es decir, en la ventana de retención de datos.  
  
-   Archivo y purga de los datos de BizTalkDTADb. El archivo es opcional, pero la purga se debe realizar periódicamente.  
  
 Hay algo que todos estos factores tienen en común: la velocidad a la que la DTA puede aceptar y procesar datos (archivo y purga).  
  
## <a name="how-the-biztalkdtadb-insert-and-processing-speed-affects-your-system"></a>Cómo influye la velocidad de inserción y de procesamiento en el sistema  
 Ahora, analicemos el seguimiento de la ruta de datos que se describe en [medir el rendimiento máximo sostenible de seguimiento](../core/measuring-maximum-sustainable-tracking-throughput.md)y evaluar el efecto de velocidad de procesamiento e inserción de BizTalkDTADb en los distintos componentes del sistema.  
  
 A partir de las tablas de cola de impresión y de datos de seguimiento, podemos imaginar que, si los procesos que mueven datos de estas tablas a la base de datos de BizTalkDTADb no pueden insertar datos en la base de datos de BizTalkDTADb, al menos, tan rápido como el tiempo de ejecución se inserta en las tablas de cola de impresión y de datos de seguimiento, las tablas de cola de impresión y de datos de seguimiento empezarán a acumular un registro. Esto no es necesariamente algo malo a corto plazo, siempre que sepa que el rendimiento del mensaje se reducirá para permitir al registro realizar la acumulación en última instancia. Sin embargo, mientras los datos sigan en las tablas de cola de impresión y de datos de seguimiento, no estarán disponibles en la base de datos BizTalkDTADb para poder consultarlos mediante consultas de seguimiento en la página Concentrador de grupo o cualquier otra herramienta.  Por lo tanto, no será de utilidad para solucionar el problema. De este modo, los períodos de acumulación esperados deben ser lo suficientemente breves, para que la información a la que se ha realizado el seguimiento continúe estando disponible en un tiempo adecuado, en caso de que surja un problema que sea necesario investigar mediante los datos de BizTalkDTADb.  
  
 A partir de la comprobación, sabemos que no son los procesos que mueven los datos de seguimiento a la base de datos de BizTalkDTADb (es decir, TDDS y TrackedMessages_Copy_BizTalkMsgBoxDb), que son los factores determinantes si se acumula un registro, sino la velocidad de la base de datos de BizTalkDTADb al aceptar la entrada. Por lo general, es el archivo de datos de la base de datos de BizTalkDTADb, que es el enlace de E/S. Es decir, será la velocidad de la unidad en la que reside el archivo de base de datos de BizTalkDTADb, la que determinará la velocidad de la DTA en general.  
  
## <a name="how-the-amount-of-data-in-biztalkdtadb-affects-io-speed"></a>Cómo influye la cantidad de datos en BizTalkDTADb en la velocidad de E/S  
 Otro factor clave relacionado con la velocidad de E/S es la cantidad de datos en la base de datos de BizTalkDTADb: como la cantidad de datos de seguimiento en la base de datos de BizTalkDTADb aumente, la velocidad de entrada y de procesamiento de la base de datos de BizTalkDTADb disminuye, dado que hay más simplemente datos para clasificar al insertar los datos nuevos, y esto afecta a la cantidad de E/S necesaria para cada inserción.  
  
 En este momento, el archivo y la purga especifican la imagen, puesto que son estos los procesos que evitan que la base de datos de BizTalkDTADb aumente demasiado para poder hacer frente a dicho crecimiento. La idea básica es asegurar que el tamaño de la base de datos de BizTalkDTADb se mantenga por debajo del nivel en el que los elementos empiezan a realizar copias de seguridad en las tablas de cola de impresión y de seguimiento de datos. Sin embargo, los procesos de purga y archivo implementados en el trabajo DTA Purge and Archive de SQL (BizTalkDTADb) también necesitan recursos (CPU, memoria y, en especial, E/S) del servidor de la base de datos de BizTalkDTADb, que se debe tener en cuenta al medir MST con seguimiento.  
  
## <a name="see-also"></a>Vea también  
 [Medir el rendimiento de seguimiento sostenible máximo](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [Escenarios de prueba para medir MST de seguimiento de DTA](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)   
 [Sugerencias y trucos para encontrar MST de seguimiento de DTA](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md)   
 [Instrucciones para ajustar el tamaño de la base de datos de seguimiento](../core/tracking-database-sizing-guidelines.md)