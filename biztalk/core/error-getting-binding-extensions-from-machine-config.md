---
title: Error al obtener las extensiones de enlace de machine.config. | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65ab48cf-575b-4db6-984a-880f7e286959
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbe53def02f42c59cf5e40380c898f47695c19da
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968802"
---
# <a name="error-getting-binding-extensions-from-machineconfig"></a>Error al obtener extensiones de enlace de machine.config.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Error al obtener extensiones de enlace de machine.config.|  
  
## <a name="explanation"></a>Explicación  
 Este error se produce cuando la configuración de enlace de una ubicación de recepción o un puerto de envío tiene una extensión de enlace definida por el usuario, pero que no está definida en el archivo machine.config. Esta situación se produce principalmente con los adaptadores de WCF-Custom y WCF-CustomIsolated.  
  
## <a name="user-action"></a>Acción del usuario  
 Defina la extensión de enlace usada en la ubicación de recepción o el puerto de envío en el archivo machine.config. Además, para que un elemento de enlace o comportamiento personalizado funcione con el adaptador de WCF-Custom, complete estos pasos:  
  
1.  Almacene el ensamblado en la memoria caché global de ensamblados (GAC)  
  
2.  Modifique el archivo machine.config (se encuentra en **%FrameworkDir%\v4.0.30319\CONFIG**).  
  
    1.  Cargar la DLL en el Editor de configuración de servicio de comportamiento (**svcConfigEditor.exe**).  
  
    2.  Guardar la configuración para un **app.config** archivo  
  
    3.  Copie y pegue el **system.servicemodel** sección de extensiones en una sección similar de machine.config. Si **system.servicemodel** sección no está presente en machine.config, puede crear uno. A continuación se proporciona un ejemplo de la sección de configuración de un archivo machine.config:  
  
        ```  
          <system.serviceModel>  
            <extensions>  
              <behaviorExtensions>  
                <add name="BizTalkWcfContractNamespaceTestServiceBehaviorExtension" type="ASB.BizTalk.Samples.BizTalkWcfContractNamespaceTestServiceBehaviorExtension, CustomBizTalkWcfBehaviors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=7631521c07cf34b4" />  
              </behaviorExtensions>  
            </extensions>  
          </system.serviceModel>  
        ```  
  
> [!NOTE]
>  El código anterior también puede agregarse a la pestaña Extensiones de WCF. Si la extensión debe estar en el lado de recepción, vea el  **\<nombre de Host\> Properties Dialog Box, extensiones de WCF** pestaña (WCF-Custom o el controlador de recepción de adaptador de WCF-CustomIsolated) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. Si la extensión debe estar en el lado de envío, vea  **\<nombre de Host\> Properties Dialog Box, extensiones de WCF** pestaña (controlador de envío de adaptador de WCF-Custom) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
 3. Cierre y vuelva a abrir la consola de administración. Debe poder ver el comportamiento personalizado en el adaptador de WCF-Custom y el puerto debería permanecer habilitado cuando lo habilite.