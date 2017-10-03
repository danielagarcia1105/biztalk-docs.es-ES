---
title: "Cómo crear un grupo de clústeres con un disco, dirección IP y el nombre Resource1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b361f721-60db-485e-9ce3-48a6871ebd79
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63310706742ffcc10de5266dda7053da79fc04fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource"></a>Cómo crear un grupo de clústeres con un disco, una dirección IP y un recurso de nombre
Para en clúster [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] componentes y dependencias para ser accesibles a través de la red a través de NetBIOS, un clúster **nombre de red** recurso debe crearse en el mismo grupo de clústeres. Para un recurso de nombre de red agrupado esté accesible a través del protocolo TCP/IP, un **dirección IP** recurso debe crearse en el mismo grupo de clúster. Algunos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dependencias también requieren el uso de un clúster **disco físico** recurso para funcionar correctamente. Para crear un grupo de clúster con una **disco físico**, **dirección IP** y **nombre de red** recursos siga estos pasos:  
  
### <a name="to-create-a-service-or-application-with-a-physical-disk-ip-address-and-network-name-resource"></a>Para crear un servicio o una apliación con un recurso Disco físico, Dirección IP y Nombre de red  
  
1.  En Windows, haga clic en **iniciar**, **programas**, **herramientas administrativas**y, a continuación, **administración de clúster de conmutación por error** para iniciar la conmutación por error Programa de administración de clúster.  
  
2.  Conmute por error todos los servicios y las aplicaciones al nodo de clúster en el que ejecuta Administración de clúster de conmutación por error. Para conmutar por error un servicio o aplicación, haga clic con el servicio o aplicación en el panel izquierdo de administración de clúster de conmutación por error, seleccione **mover este servicio o aplicación a otro nodo** y haga clic para seleccionar el nodo de destino.  
  
    > [!NOTE]
    >  El nodo de clúster que hospeda los recursos de clúster de ejecución también es conocido como el **active** nodo. El nodo de clúster que hospeda los recursos de clúster no están en ejecución es también conocido como el **pasivo** nodo.  
  
3.  En el panel izquierdo, haga clic en **servicios y aplicaciones**, haga clic en **configurar un servicio o aplicación** para iniciar el Asistente para alta disponibilidad y, a continuación, haga clic en **siguiente**.  
  
4.  Haga clic para seleccionar **servidor de archivos** y haga clic en **siguiente**.  
  
    > [!NOTE]
    >  Seleccionar **servidor de archivos** en este punto se realiza como una manera sencilla de crear un grupo de clústeres con un recurso de disco.  
  
5.  En el **punto de acceso de cliente** página del Asistente para alta disponibilidad escriba un nombre de red único en la **nombre** cuadro, por ejemplo *BizTalkCluster*, escriba una dirección IP disponible dirección en **dirección**y, a continuación, haga clic en **siguiente**.  
  
6.  En el **Seleccionar almacenamiento** página, haga clic para seleccionar un recurso de disco disponible y, a continuación, haga clic en **siguiente**.  
  
7.  En el **confirmación** página haga clic en **siguiente** para crear el grupo de clúster.  
  
8.  En el **resumen** página haga clic en **finalizar**.