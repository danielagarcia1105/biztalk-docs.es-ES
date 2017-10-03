---
title: Contadores de rendimiento del adaptador de archivo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 343465b4-6b20-4a24-b4b1-138548c572cc
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 617c3fc2821c9b9aa1aba690d27a9b48dc1116c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="file-adapter-performance-counters"></a>Contadores de rendimiento del adaptador de archivo
Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.  
  
 Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **BizTalk: adaptador de recepción** y **BizTalk: adaptador de envío** categorías de objetos de rendimiento:  
  
|**Categoría**|**Contador**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk: adaptador de recepción|Bytes recibidos|Número total de bytes recibidos por el adaptador de recepción de archivo. El contador aumenta cuando el adaptador lee completamente un mensaje desde el sistema de archivos.|  
||Bytes recibidos/seg.|Número de bytes recibidos por el adaptador de recepción de archivo por segundo. El contador sólo es aplicable a los mensajes que el adaptador de archivo ha leído completamente desde el sistema de archivos.|  
||Intentos de eliminación|Número de veces que el adaptador de recepción de archivo intenta eliminar un archivo que se ha leído.|  
||Bloquear errores|Número de veces que el adaptador de recepción de archivo no pudo bloquear el archivo.|  
||Bloquear errores/s|Número de veces que el adaptador de recepción de archivo no pudo bloquear el archivo por segundo.|  
||Mensajes recibidos|Número total de mensajes recibidos por el adaptador de recepción de archivo. El contador aumenta cuando el adaptador de recepción de archivo lee completamente un mensaje desde el sistema de archivos.|  
||Mensajes recibidos/s|Número de mensajes recibidos por el adaptador de recepción de archivo por segundo. El contador sólo se aplica a los mensajes que el adaptador de recepción de archivo ha leído completamente desde el sistema de archivos.|  
||Tiempo de generación de lote|Promedio de tiempo que emplea el adaptador de recepción de archivo en generar un lote.|  
|BizTalk: adaptador de envío|Bytes enviados|Número total de bytes enviados por el adaptador de envío de archivo. El contador sólo aumenta con mensajes que se han escrito totalmente en el sistema de archivos.|  
||Bytes enviados/seg.|Número de bytes enviados por el adaptador de envío de archivo por segundo. El contador sólo se aplica a mensajes que se han escrito totalmente en el sistema de archivos.|  
||Mensajes enviados|Número total de mensajes enviados por el adaptador de envío de archivo. El contador sólo aumenta con mensajes que se han escrito totalmente en el sistema de archivos.|  
||Mensajes enviados/s|Número de mensajes enviados por el adaptador de envío de archivo por segundo. El contador sólo se aplica a mensajes que se han escrito totalmente en el sistema de archivos.|  
  
## <a name="to-access-performance-counters"></a>Para tener acceso a los contadores de rendimiento  
 Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.  
  
#### <a name="if-you-are-using-windows-2008"></a>Si está usando Windows 2008  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.  
  
2.  En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.  
  
3.  En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **BizTalk** objeto de contador de rendimiento y seleccione los contadores que desea supervisar  
  
4.  En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.  Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**>.  
  
5.  Después de agregar los contadores, haga clic en **Aceptar**.  
  
     Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.  
  
## <a name="see-also"></a>Vea también  
 [Planear el rendimiento sostenido de](../core/planning-for-sustained-performance.md)