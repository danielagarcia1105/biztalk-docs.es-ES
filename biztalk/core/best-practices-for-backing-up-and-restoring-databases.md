---
title: "Prácticas recomendadas para realizar copias de seguridad y restaurar bases de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, maintaining
- restoring, best practices
- best practices, backing up
- backing up, restoring
- backing up, best practices
- maintaining, best practices
- best practices, restoring
ms.assetid: 649ca56b-3cc1-49ad-9f74-ba1521e65ee1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2543f09c5118e58bd18ea2add113811fb733d884
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-backing-up-and-restoring-databases"></a>Prácticas recomendadas para realizar copia de seguridad y restaurar las bases de datos
Revise las siguientes prácticas recomendadas para garantizar la posibilidad de llevar a cabo una copia de seguridad de las bases de datos de BizTalk Server, así como de restaurarlas.  
  
-   **Desarrollar la copia de seguridad y estrategias de restauración y se prueban.**  
  
     Con un buen plan, es posible recuperar los datos con rapidez si se pierden a causa de un error de hardware.  
  
-   **Administrar espacio en disco y archivar archivos de copia de seguridad anteriores.**  
  
     El trabajo de copia de seguridad de BizTalk Server no elimina archivos de copia de seguridad obsoletos, por lo que la administración de este tipo de archivos resulta necesaria para conservar espacio en disco. Después de crear una nueva copia de seguridad completa de las bases de datos, debería mover los archivos de copia de seguridad obsoletos a un dispositivo de almacenamiento de archivado para recuperar espacio en el disco principal.  
  
-   **No almacene las copias de seguridad en el mismo equipo o disco que copia de seguridad.**  
  
     Debe especificar un equipo o un disco para la copia de seguridad distinto del equipo en el que se encuentren los datos originales. De lo contrario, perderá todos los datos si se produce un error de hardware.  
  
-   **Conservar copias.**  
  
     Conserve al menos tres copias de los medios. Conserve, como mínimo, una copia fuera de las instalaciones, en un entorno sometido a un control adecuado.  
  
-   **Realizar restauraciones de prueba.**  
  
     Efectúe una restauración de prueba al menos una vez al mes para comprobar que la copia de seguridad de los archivos se realiza correctamente. La restauración de prueba puede revelar problemas de hardware que no se detectan al comprobar que el software funciona correctamente. No espere a que se produzca un error del disco duro para ver si es posible restaurar el sistema y las bases de datos.  
  
-   **Proteger los dispositivos y medios.**  
  
     Proteja los dispositivos de almacenamiento y los medios de copia de seguridad. Una persona puede obtener acceso a los datos de un medio robado si los restaura en un servidor del que sea administrador.  
  
-   **Proceso de restauración y supervisar la copia de seguridad.**  
  
     Para asegurarse de que el proceso de restauración y de copia de seguridad se realiza correctamente, debería supervisar los trabajos del Agente SQL Server utilizados para realizar una copia de seguridad del servidor BizTalk Server y su restauración.  
  
## <a name="see-also"></a>Vea también  
 [Copia de seguridad y restaurar las bases de datos de servidor BizTalk Server](../core/backing-up-and-restoring-the-biztalk-server-databases.md)