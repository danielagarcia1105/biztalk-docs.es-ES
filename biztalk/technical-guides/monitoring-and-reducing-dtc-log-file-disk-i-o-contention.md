---
title: "Contención de E/S de disco de archivos de supervisión y reducir el registro de DTC | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8b968dd-216e-454f-9224-aaf92ffd363b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7206c4220153ee95f78e5744a2df2ff7eeb3541e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-and-reducing-dtc-log-file-disk-io-contention"></a>Supervisión y reducir la contención de E/S de disco del archivo de registro DTC
El archivo de registro de coordinador de transacciones distribuidas (DTC) puede convertirse en un cuello de botella de E/S de disco en entornos con muchas transacciones. Esto es especialmente cierto cuando se utiliza adaptadores que admiten transacciones, por ejemplo, SQL Server, MSMQ y MQSeries, o en un entorno de cuadro de mensajes múltiples. Adaptadores transaccionales usen transacciones DTC y entornos de cuadro de mensajes múltiples hacen un amplio uso de transacciones DTC.  
  
## <a name="monitoring-usage-in-clustered-and-non-clustered-environments"></a>Supervisar el uso en entornos en clúster y no clúster  
 Para asegurarse de que el archivo de registro DTC no se convierten en un cuello de botella de E/S de disco, debe supervisar el uso de E/S del disco donde reside el archivo de registro DTC en el servidor de base de datos de SQL Server de disco.  
  
 En un entorno donde está en el clúster de SQL Server, esto no es tanto un problema porque el archivo de registro ya estarán en una unidad compartida, que probablemente será una unidad de SAN rápida con varios ejes. Sin embargo, todavía debe supervisar el uso de E/S de disco ya que puede convertirse en un cuello de botella en entornos no agrupado o si el archivo de registro DTC en un disco compartido con otros archivos de uso intensivo del disco.  
  
## <a name="troubleshooting-dtc"></a>Solución de problemas de DTC  
 Para obtener información sobre solución de problemas de DTC, vea "Solucionar problemas con MSDTC" en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237).  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Configurar Windows Server](../technical-guides/checklist-configuring-windows-server.md)