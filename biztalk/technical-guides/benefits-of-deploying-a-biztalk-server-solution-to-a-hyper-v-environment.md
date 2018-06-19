---
title: Entorno virtualizado de posibles ventajas de implementar una solución de BizTalk Server en un Hyper-V | Documentos de Microsoft
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
ms.openlocfilehash: 9602a48b0deb4eeddc6f10b2d529d68d94cc781a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295932"
---
# <a name="potential-benefits-of-deploying-a-biztalk-server-solution-to-a-hyper-v-virtualized-environment"></a>Entorno virtualizado de posibles ventajas de implementar una solución de BizTalk Server en un Hyper-V
En este tema se describe algunas de las ventajas de la implementación de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución para un entorno virtualizado de Hyper-V.  
  
## <a name="benefits-of-running-a-biztalk-server-solution-on-a-hyper-v-virtualized-environment"></a>Ventajas de una solución de BizTalk Server en ejecución en un Hyper-V entorno virtualizado  
 La implementación de la solución de BizTalk Server para que se ejecute en un entorno virtualizado de Hyper-V ofrece la flexibilidad y la funcionalidad siguiente:  
  
-   **Capacidad de definir varios límites de seguridad lógicos distintos en un único equipo físico -** Hyper-V permite la creación de los límites de seguridad lógico distinto o particiones dentro de un recurso de hardware físico único. Una partición es una sola unidad lógica de aislamiento, admitido por el hipervisor, en la que se ejecutan sistemas operativos. Por ejemplo, podría crear varios grupos de BizTalk Server para ejecutarse en un único equipo host de Hyper-V, mientras que no sería capaz de hacer esto al instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el sistema operativo de host de un único equipo host.  
  
-   **Facilidad de implementación y administración de-** consolidación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en menos servidores físicos simplifica la implementación. [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]usa un método simplificado para implementaciones en equipos físicos y virtuales mediante el uso de archivos .vhd. Además, una completa solución de administración de Hyper-V está disponible con System Center Virtual Machine Manager. Para obtener más información acerca de System Center Virtual Machine Manager, consulte [http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303).  
  
-   **Error de compatibilidad con tolerancia a través de clústeres de Hyper-V -** porque Hyper-V es una aplicación compatible con clústeres, Windows Server 2008 proporciona compatibilidad para las máquinas virtuales creadas en un entorno virtualizado de Hyper-V de agrupación en clústeres de host nativo.  
  
-   **Facilidad de ampliación horizontal -** potencia de procesamiento adicional, el ancho de banda de red y la capacidad de almacenamiento se pueden incluir para su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución rápida y fácilmente por prorratear más recursos disponibles desde el equipo host para el invitado máquinas virtuales. Esto puede requerir que el equipo host está actualizado o que las máquinas virtuales invitadas se mueven a un equipo host mayor capacidad. La característica de migración en vivo de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] le permite mover máquinas virtuales en ejecución en el equipo físico recomendado para el rendimiento, el ajuste de escala o la consolidación óptimo sin afectar a los usuarios.  
  
-   **Consolidación de recursos de hardware -** varios servidores físicos que se pueden consolidar fácilmente en comparativamente menos servidores mediante la implementación de virtualización con Hyper-V. Consolidación permite un uso completo de los recursos de hardware implementado.  
  
 Para obtener más información detallada proporciona información sobre las características y ventajas de Hyper-V, consulte [virtualización con Hyper-V](http://go.microsoft.com/fwlink/?LinkID=202438).