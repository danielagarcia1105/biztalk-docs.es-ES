---
title: Entorno virtualizado de posibles ventajas de implementar una solución de BizTalk Server en un Hyper-V | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 588c70f0-68f0-4e58-8f3d-aa6834397bd4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c88a8dcc6386b6030d4ca429010b6db1acfb81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024450"
---
# <a name="potential-benefits-of-deploying-a-biztalk-server-solution-to-a-hyper-v-virtualized-environment"></a>Entorno virtualizado de posibles ventajas de implementar una solución de BizTalk Server en un Hyper-V
En este tema se describe algunas de las ventajas de implementar su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución a un entorno virtualizado de Hyper-V.  
  
## <a name="benefits-of-running-a-biztalk-server-solution-on-a-hyper-v-virtualized-environment"></a>Ventajas de la ejecución de una solución de BizTalk Server en un Hyper-V entorno virtualizado  
 Implementar la solución de BizTalk Server para ejecutarse en un entorno virtualizado de Hyper-V proporciona la flexibilidad y la funcionalidad siguiente:  
  
- **Capacidad de definir varios límites de seguridad lógicos distintos en un único equipo físico -** Hyper-V admite la creación de los límites de seguridad lógico distinto o particiones dentro de un recurso de hardware físico único. Una partición es una única unidad lógica de aislamiento admitido por el hipervisor, en el que se ejecutan los sistemas operativos. Por ejemplo, podría crear varios grupos de BizTalk Server para ejecutar en un único equipo host de Hyper-V, mientras que no sería capaz de hacer esto al instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el sistema operativo de host de un único equipo host.  
  
- **Facilidad de implementación y administración –** consolidación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] simplifica la implementación de equipos en menos servidores físicos. [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] mediante el uso de archivos .vhd, usa un método simplificado para implementaciones en equipos físicos y virtuales. Además, una completa solución de administración de Hyper-V está disponible con System Center Virtual Machine Manager. Para obtener más información acerca de System Center Virtual Machine Manager, consulte [ http://go.microsoft.com/fwlink/?LinkID=111303 ](http://go.microsoft.com/fwlink/?LinkID=111303).  
  
- **Error de compatibilidad con tolerancia a través de clústeres de Hyper-V -** porque Hyper-V es una aplicación compatible con clústeres, Windows Server 2008 ofrece compatibilidad con clústeres para las máquinas virtuales creadas en un entorno virtualizado de Hyper-V de host nativo.  
  
- **Facilidad de escalabilidad horizontal -** potencia de procesamiento adicional, el ancho de banda de red y la capacidad de almacenamiento se pueden incluir para su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución rápida y fácilmente mediante prorrateo recursos adicionales disponibles desde el equipo host al invitado máquinas virtuales. Esto puede requerir que se actualiza el equipo host o que las máquinas virtuales invitadas se mueven a un equipo host con más capacidad. La característica de migración en vivo de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] permite mover máquinas virtuales en ejecución en el equipo físico mejor rendimiento, escala o consolidación óptimo sin afectar a los usuarios.  
  
- **Consolidación de recursos de hardware -** varios servidores físicos se pueden consolidar fácilmente en un número comparativamente menor de servidores mediante la implementación de virtualización con Hyper-V. La consolidación se adapta a un uso completo de los recursos de hardware implementado.  
  
  Para obtener más información detallada proporciona información sobre las características y beneficios de Hyper-V, consulte [virtualización con Hyper-V](http://go.microsoft.com/fwlink/?LinkID=202438).