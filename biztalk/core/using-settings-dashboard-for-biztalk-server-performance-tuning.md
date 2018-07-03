---
title: Mediante el panel de configuración de BizTalk Server Performance Tuning | Microsoft Docs
description: Usar el panel de configuración de administración de BizTalk Server para actualizar la configuración de la instancia de host, el host y el grupo
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb1ddac-1e8f-4928-9c70-8326ae64a734
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b6ed0c44bea5abaaac7b2009e27819e66043957
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974861"
---
# <a name="use-settings-dashboard-for-biztalk-server-performance-tuning"></a>Usar el panel de configuración para el servidor BizTalk Server optimización del rendimiento

## <a name="overview"></a>Información general
Con el panel de configuración, puede ajustar ampliamente la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para optimizar su rendimiento. También puede modificar la configuración del grupo de BizTalk, el host de BizTalk y la instancia de host de BizTalk.  
  
- **Configuración de nivel de grupo**: el nivel de grupo, puede usar el [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] para establecer propiedades como el intervalo de actualización de configuración, tamaño de lote máximo del mensaje, seguimiento de nivel de grupo, etcetera. Esta configuración se aplica a todas las máquinas en un grupo de BizTalk.  
  
- **Configuración de nivel de host**: en el nivel de host, puede modificar la configuración, como el seguimiento de host, las propiedades relacionadas con la limitación basada en recursos, las propiedades relacionadas con la limitación del proceso de mensaje y propiedades relacionadas con la limitación de orquestaciones. Estas opciones se aplican a todas las instancias del host seleccionado.  
  
- **Configuración del nivel de instancia de host**: en el nivel de instancia de host, puede modificar la configuración de .NET CLR y propiedades relacionadas con la limitación de memoria de orquestación. Estas opciones se aplican solo a la instancia de host seleccionada.  
  
  Para obtener más información sobre el grupo de BizTalk, el BizTalk Host y configuración de la instancia de Host de BizTalk, consulte [cómo modificar la configuración del grupo](../core/how-to-modify-group-settings.md), [cómo modificar la configuración del Host](../core/how-to-modify-host-settings.md), y [cómo modificar el Host Configuración de instancia](../core/how-to-modify-host-instance-settings.md).  
  
  El panel de configuración le permite importar y exportar la configuración de BizTalk a través de implementaciones que no es necesario que sean idénticas. Mediante el uso de la interfaz de usuario, puede asignar los hosts y las instancias de hosts desde implementaciones de destino hasta implementaciones de origen. Esto le ayudará a aplicar la configuración a un entorno donde los nombres de host y equipo, o sus respectivos números, son diferentes. Para obtener más información acerca de la importación/exportación de configuración de BizTalk, consulte [importación o exportación usando configuración de panel de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md).  
  
## <a name="see-also"></a>Vea también  
 [Administrar la configuración de rendimiento de servidor BizTalk Server](../core/managing-biztalk-server-performance-settings.md)