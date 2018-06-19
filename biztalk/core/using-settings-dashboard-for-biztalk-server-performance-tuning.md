---
title: Mediante el panel de configuración de BizTalk Server Performance Tuning | Documentos de Microsoft
description: Usar el panel de configuración en administración de BizTalk Server para actualizar el grupo, el host y la configuración de la instancia de host
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
ms.openlocfilehash: be1978f92cbbbce945cb7b5a97458577cbf6f725
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287404"
---
# <a name="use-settings-dashboard-for-biztalk-server-performance-tuning"></a>Usar el panel de configuración para el servidor BizTalk Server ajuste del rendimiento

## <a name="overview"></a>Información general
Con el panel de configuración, puede ajustar ampliamente la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para optimizar su rendimiento. También puede modificar la configuración del grupo de BizTalk, el host de BizTalk y la instancia de host de BizTalk.  
  
-   **Configuración de nivel de grupo**: en el nivel de grupo, puede usar el [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] para establecer propiedades como el intervalo de actualización de configuración, tamaño de lote máximo del mensaje, seguimiento de nivel de grupo, etcetera. Esta configuración se aplica a todos los equipos en un grupo de BizTalk.  
  
-   **Configuración de nivel de host**: en el nivel de host, puede modificar la configuración como seguimiento de host, propiedades relacionadas con la limitación basada en recursos, propiedades relacionadas con la limitación de proceso de mensajes y propiedades relacionadas con la limitación de orquestaciones. Estas opciones se aplican a todas las instancias del host seleccionado.  
  
-   **Configuración de nivel de instancia de host**: en el nivel de instancia de host, puede modificar la configuración de .NET CLR y propiedades relacionadas con la limitación de memoria de orquestación. Estas opciones se aplican solo a la instancia de host seleccionada.  
  
 Para obtener más información sobre el grupo de BizTalk, el Host de BizTalk y la configuración de la instancia de Host de BizTalk, consulte [cómo modificar la configuración del grupo de](../core/how-to-modify-group-settings.md), [cómo modificar la configuración del Host](../core/how-to-modify-host-settings.md), y [cómo modificar Host Configuración de instancia](../core/how-to-modify-host-instance-settings.md).  
  
 El panel de configuración le permite importar y exportar la configuración de BizTalk a través de implementaciones que no es necesario que sean idénticas. Mediante el uso de la interfaz de usuario, puede asignar los hosts y las instancias de hosts desde implementaciones de destino hasta implementaciones de origen. Esto le ayudará a aplicar la configuración a un entorno donde los nombres de host y equipo, o sus respectivos números, son diferentes. Para obtener más información acerca de cómo importar o exportar la configuración de BizTalk, consulte [importación o exportación panel de configuración de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md).  
  
## <a name="see-also"></a>Vea también  
 [Administrar la configuración de rendimiento de servidor BizTalk Server](../core/managing-biztalk-server-performance-settings.md)