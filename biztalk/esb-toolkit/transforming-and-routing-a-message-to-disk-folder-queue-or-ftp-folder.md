---
title: Transformar y enrutar un mensaje a la carpeta de disco, la cola o la carpeta FTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bfdbc38-6663-4d95-a0ed-57fec0245b9f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcbc9d42fbed5dfd73aee910ba2e1a40da595658
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009845"
---
# <a name="transforming-and-routing-a-message-to-disk-folder-queue-or-ftp-folder"></a>Transformar y enrutar un mensaje a la carpeta de disco, la cola o la carpeta FTP
En este caso de uso, ESB transforma un mensaje enviado a través del servicio Web de itinerario o cualquier en rampa. Búsqueda de resolución dinámica de tipo FILE, FTP o ubicación de la cola determina el nombre de asignación (para la transformación) y el extremo de destino para el mensaje, como se muestra en la figura 1.  
  
 ![Transformación de carpeta de disco](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3-TransformingDiskFolder")  
  
 **Figura 1**  
  
 **Transformar y enrutar un mensaje a una carpeta del disco**  
  
 El ejemplo de resolución dinámica que se incluye con [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso. Muestra cómo utilizar los componentes para resolver la ubicación del extremo dinámicamente, establecer las propiedades de enrutamientos y resolver y ejecutar asignaciones de BizTalk Server en el nivel de mensajería, sin utilizar una orquestación. También muestra los patrones de mensajería unidireccionales y bidireccionales.  
  
 Una extensión de este caso de uso es una solución sencilla de enrutamiento que enruta un mensaje entrante a un archivo, FTP o ubicación de la cola sin el paso adicional de transformación.  
  
 Para obtener más información, consulte [instalar y ejecutar el ejemplo de resolución dinámicos](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).