---
title: Procedimientos recomendados para el seguimiento de datos de instancias y mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HAT, best practices
- best practices, HAT
ms.assetid: 2ac5c87b-2059-4912-9cec-2ae4eaac56df
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a6f673b0a70903575918eb87dc4bd8edc9841e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-message-and-instance-data-tracking"></a>Prácticas recomendadas para el seguimiento de datos de instancias y mensajes
Revise las siguientes prácticas recomendadas para usar datos históricos y de seguimiento.  
  
-   **Revise las consideraciones de seguridad para usar datos históricos y de seguimiento**  
  
    -   Para obtener más información acerca de las consideraciones de seguridad para los datos históricos y de seguimiento, vea [consideraciones de seguridad para el mensaje y seguimiento de datos de instancia](../core/security-considerations-for-message-and-instance-data-tracking.md).  
  
-   **Asegúrese de que el servicio Agente SQL Server se ejecuta en todas las bases de datos de cuadro de mensajes**  
  
    -   El Agente SQL Server hace que los cuerpos de mensajes disponibles estén disponibles para WMI y los datos históricos y de seguimiento. Esto permite ejecutar trabajos para limpiar las bases de datos de cuadro de mensajes. Para obtener información adicional acerca de Agente SQL Server, vea Libros en pantalla de SQL Server.  
  
-   **Habilitar el seguimiento de cuerpos de mensaje**  
  
    -   El seguimiento de partes de mensaje es necesario para guardar mensajes una vez completado el procesamiento de instancias de servicios.  
  
-   **Configurar el seguimiento en función de sus necesidades empresariales**  
  
    -   Antes de poder visualizar datos históricos y de seguimiento, tendrá que configurar el seguimiento mediante la consola de administración de BizTalk Server. Al habilitar o deshabilitar las opciones de seguimiento, debe tenerse en cuenta una serie de consideraciones. Cuantos más datos sean objeto de seguimiento, mayor será el ritmo al que aumentará el tamaño de la base de datos de seguimiento de BizTalk (BizTalkDTADb), lo que, a su vez, puede afectar negativamente al rendimiento del tiempo de ejecución. Para obtener más información, consulte [configuración de seguimiento mediante la consola de administración de BizTalk Server](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef).  
  
-   **Seleccione el tipo adecuado de seguimiento para solucionar problemas o auditoría**  
  
    -   Para solucionar problemas en un entorno de desarrollo, o en un entorno de producción o de ensayo, debería habilitar todas las opciones de seguimiento, de modo que resulte posible ver eventos de artefactos, propiedades de mensaje, cuerpos de mensaje y eventos de orquestación de forma detallada. Con ello, se proporciona un nutrido conjunto de datos sometidos a seguimiento que puede utilizarse para volver a crear la secuencia de eventos del sistema y depurar la aplicación.  
  
    -   Para efectuar una auditoría de nivel de producción, seleccione cuidadosamente los eventos que desea auditar y, seguidamente, habilite el seguimiento sólo para esos eventos. Por ejemplo, muchas empresas desean poder demostrar que un mensaje entró en el sistema y que salió de él. Para cumplir este propósito, debería habilitar el seguimiento de entrada y de salida, respectivamente, en los puertos de envío y recepción que corresponda. Si resulta necesario, puede agregar el seguimiento de partes de mensaje y de propiedades de mensaje.  
  
    -   Para medir los indicadores clave de rendimiento (KPI) o del progreso cuya medición se realiza de acuerdo con la consecución de hitos económicos especificados, debería utilizar el seguimiento de Supervisión de la actividad económica (BAM). El seguimiento de BAM tiene capacidades limitadas en cuanto al seguimiento y almacenamiento de cuerpos de mensaje; de modo que, si esto último resulta importante, se deberían usar los datos históricos y de seguimiento junto con el seguimiento de BAM. Para obtener más información acerca del seguimiento de BAM, consulte [usando Business Activity Monitoring](../core/using-business-activity-monitoring.md).  
  
-   **Archivar y purgar los datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb) de forma periódica**  
  
    -   Si ha habilitado el seguimiento, debería archivar y purgar regularmente los datos de la base de datos de seguimiento de BizTalk para contribuir al mantenimiento de un tamaño adecuado de la base de datos, lo que, a su vez, ayuda a mejorar el rendimiento del sistema. Para obtener más información, consulte [archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md).  
  
## <a name="see-also"></a>Vea también  
 [Datos de instancia y los mensajes de seguimiento de visualización](../core/viewing-tracked-message-and-instance-data.md)