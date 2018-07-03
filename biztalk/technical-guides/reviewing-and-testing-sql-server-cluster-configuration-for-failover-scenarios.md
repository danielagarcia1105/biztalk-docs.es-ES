---
title: Revisar y probar SQL Server la configuración para escenarios de conmutación por error del clúster | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dbeb383-5b38-4467-acf8-2a5b244e5fa9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 981a879a5dad68bfb423a03b82e11fb646f912c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973261"
---
# <a name="reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios"></a>Revisar y probar la configuración de clúster SQL Server para escenarios de conmutación por error
Agrupación en clústeres de Windows y SQL Server permiten ejecutar SQL Server en modo activo/activo, donde cada nodo del clúster es "activas" y en funcionamiento las instancias de SQL Server de uno o más. Esto le permitiría, por ejemplo, para que la base de datos de cuadro de mensajes en un nodo y todos los demás [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos en el otro nodo. Esto permite maximizar el uso de hardware de clúster.  
  
 Sin embargo, si usa esta configuración, debe comprobar que cada nodo puede controlar al mismo tiempo la carga de todas las instancias de SQL Server durante una conmutación por error de nodo de SQL Server Cluster Server.  
  
## <a name="evaluating-failover-for-an-activeactive-cluster"></a>Evaluar la conmutación por error para un clúster activo/activo  
 Consideraciones al comprobar que un nodo único puede controlar la carga de todas las instancias de SQL Server en el caso de un nodo de clúster de SQL Server conmutación por error incluyen:  
  
- ¿El nodo de conmutación por error tiene suficientes recursos de CPU?  
  
- ¿El nodo de conmutación por error tiene suficiente memoria?  
  
- ¿Hay suficiente ancho de banda de red?  
  
- ¿El nodo de conmutación por error puede controlar la contención de E/S de disco mayor?  
  
  Al probar la conmutación por error, se deben evaluar los escenarios siguientes:  
  
- Corte del suministro eléctrico en el servidor activo  
  
- Corte del suministro eléctrico en el servidor pasivo  
  
- Pérdida de conexión del disco  
  
- Interrumpa la conexión de red pública en el nodo activo  
  
- Interrumpa la conexión de red privada en el nodo activo  
  
- Interrumpa la conexión de red pública en el nodo pasivo  
  
- Interrumpa la conexión de red privada en el nodo pasivo  
  
- Servicio de SQL Server con error  
  
- Servicio Agente SQL Server con errores  
  
## <a name="using-an-activeactivepassive-cluster"></a>Uso de un clúster activo/activo/pasivo  
 Si determina que un nodo no puede controlar todas las instancias de SQL Server en un escenario de conmutación por error, una alternativa es usar un modelo de agrupación en clústeres activo/activo/pasivo. El modelo de agrupación en clústeres activo/activo/pasivo aumenta en gran medida la probabilidad de que siempre habrá un nodo pasivo disponibles para escenarios de conmutación por error.  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: configuración de SQL Server](~/technical-guides/checklist-configuring-sql-server.md)