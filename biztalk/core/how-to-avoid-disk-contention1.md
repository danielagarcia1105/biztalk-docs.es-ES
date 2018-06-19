---
title: Cómo evitar disco Contention1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8b4f8e10-16b0-45f9-8787-da16266da980
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 702665046dbaee77412675e4be0edc602dd9e7e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248260"
---
# <a name="how-to-avoid-disk-contention"></a>Cómo evitar la contención del disco
BizTalk Server está diseñado como un sistema permanente donde, en el caso de escenarios de alto rendimiento, el cuadro de mensajes puede sufrir contenciones severas. Esta contención puede verse agravada por discos lentos. Si los discos son lentos (bajo % de tiempo de inactividad del disco), pueden provocar que SQL mantenga los bloqueos durante más tiempo (tiempos de espera de bloqueos altos) y, por tanto, que crezcan las tablas (cola de impresión y de aplicación) del cuadro de mensajes. Esto ocasiona que la base de datos se inunde y se vea limitada, con lo que el rendimiento global sostenible será inferior.  
  
 Para evitar la contención del disco, se recomienda que realice lo siguiente:  
  
-   Use discos de alta velocidad (varios ejes).  
  
-   Cuando sea posible, implemente las bases de datos en una SAN de alta velocidad. Si hay varias bases de datos que comparten los mismos discos, se recomienda configurarlos en discos dedicados independientes. Además, es aconsejable separar los archivos MDF y LDF para la base de datos del cuadro de mensajes en diferentes discos.  
  
-   En caso de que SQL necesite de la CPU, considere la posibilidad de separar la base de datos del cuadro de mensajes en un servidor dedicado que sea independiente de las bases de datos de seguimiento.  
  
-   Después de configurar un servidor dedicado para la base de datos de cuadro de mensajes, considere la posibilidad de escalar verticalmente mediante la actualización de la CPU y la adición de más CPU. Supervise la unidad local en el servidor de SQL Server como los registros de MSDTC se guardan en la unidad local (C:\WINDOWS\system32\Msdtc).  
  
-   Si hay contención en la unidad local debido al archivo de paginación o al registro MSDTC, intente moverlos a una unidad independiente.