---
title: Configuración para escenarios de conmutación por error de clúster de revisar y probar SQL Server | Documentos de Microsoft
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
ms.openlocfilehash: d8e7bed17960700aee84631801e3e26cb05b25c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302220"
---
# <a name="reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios"></a>Revisar y probar la configuración de clúster SQL Server para escenarios de conmutación por error
Agrupación en clústeres de Windows y SQL Server permiten ejecutar SQL Server en modo activo/activo, donde cada nodo del clúster es "activos" y en funcionamiento instancias de SQL Server de uno o más. Esto le permitirá, por ejemplo, para que la base de datos de cuadro de mensajes en un nodo y todos los demás [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos en el otro nodo. Esto permite maximizar el uso de hardware de clúster.  
  
 Sin embargo, si usa esta configuración, debe comprobar que cada nodo al mismo tiempo puede controlar la carga de todas las instancias de SQL Server durante una conmutación por error de SQL Server cluster nodos.  
  
## <a name="evaluating-failover-for-an-activeactive-cluster"></a>Evaluación de conmutación por error para un clúster activo/activo  
 Consideraciones al comprobar que un único nodo puede controlar la carga de todas las instancias de SQL Server en el caso de un nodo de clúster de SQL Server conmutación por error incluyen:  
  
-   ¿El nodo de conmutación por error tiene suficientes recursos de CPU?  
  
-   ¿El nodo de conmutación por error tiene suficiente memoria?  
  
-   ¿Hay suficiente ancho de banda de red?  
  
-   ¿Puede controlar el nodo de conmutación por error la contención de E/S de disco mayor?  
  
 Al probar la conmutación por error deben evaluarse los siguientes escenarios:  
  
-   Error de alimentación en el servidor activo  
  
-   Error de alimentación en el servidor pasivo  
  
-   Pérdida de conexión de disco  
  
-   Interrumpe la conexión de red pública en el nodo activo  
  
-   Interrumpe la conexión de red privada en el nodo activo  
  
-   Interrumpe la conexión de red pública en el nodo pasivo  
  
-   Interrumpe la conexión de red privada en el nodo pasivo  
  
-   Error servicio de SQL Server  
  
-   Error al servicio de agente SQL Server  
  
## <a name="using-an-activeactivepassive-cluster"></a>Uso de un clúster activo/activo/pasivo  
 Si determina que un nodo no puede controlar todas las instancias de SQL Server en un escenario de conmutación por error, una alternativa es usar un modelo de agrupación en clústeres activo/activo/pasivo. El modelo de agrupación en clústeres activo/activo/pasivo aumenta en gran medida la probabilidad de que siempre habrá un nodo pasivo disponibles para los escenarios de conmutación por error.  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Configurar SQL Server](~/technical-guides/checklist-configuring-sql-server.md)