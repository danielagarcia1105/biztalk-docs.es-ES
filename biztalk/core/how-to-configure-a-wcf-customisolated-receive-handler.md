---
title: Cómo configurar controlador de recepción de un WCF-CustomIsolated | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e90add2-1a5e-4509-a98c-b3c297b4213f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37c20d02f1051e8448eb50a7c60c57f93a524238
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022538"
---
# <a name="how-to-configure-a-wcf-customisolated-receive-handler"></a>Configuración de un controlador de recepción de WCF-CustomIsolated
Debe configurar las propiedades del controlador de recepción si desea que el adaptador de WCF-CustomIsolated busque la extensión de comportamiento personalizado en otras ubicaciones aparte de machine.config.  
  
## <a name="why-should-wcf-customisolated-adapter-look-up-custom-behavior-extensions-from-locations-other-than-machineconfig"></a>¿Por qué debería el adaptador de WCF-CustomIsolated buscar las extensiones de comportamiento personalizado en ubicaciones que no sean el archivo machine.config?  
 Extensiones de comportamiento personalizado utilizadas por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se registran en el archivo machine.config. Antes de cargar las extensiones de comportamiento, el adaptador WCF-CustomIsolated busca las extensiones de comportamiento en el archivo machine.config. Sin embargo, este archivo se usa para almacenar información de configuración que se requiere en todas las aplicaciones que se ejecutan en un equipo determinado. Por otro lado, es posible que las extensiones de comportamiento personalizado de WCF solo sean necesarias para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y no para todas las aplicaciones que se ejecutan en el equipo. Por lo tanto, aunque las extensiones de comportamiento personalizado se pueden almacenar en el archivo machine.config, esta no es la ubicación óptima.  
  
 Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], las propiedades del controlador de adaptador proporcionan una ubicación adicional desde la que el adaptador de WCF-CustomIsolated puede buscar las extensiones de comportamiento personalizado. Tenga en cuenta que esto no reemplaza a las extensiones de comportamiento que ya están disponibles en el archivo machine.config.  
  
### <a name="additional-considerations"></a>Consideraciones adicionales  
 Tenga en cuenta los puntos siguientes al configurar las propiedades del controlador de recepción de WCF-CustomIsolated:  
  
-   Las extensiones del controlador de envío personalizado deben estar disponibles en el archivo machine.config o en las propiedades del controlador de adaptador. No se deben duplicar las extensiones de comportamiento personalizado en ambas ubicaciones.  
  
-   Si la extensión de comportamiento personalizado ya está disponible en el archivo machine.config e intenta establecer la misma extensión de comportamiento para las propiedades del controlador de adaptador, se producirá un error cuando intente establecer la propiedad.  
  
-   Si la extensión de comportamiento personalizado ya está establecida para las propiedades del controlador de adaptador y actualiza el archivo machine.config con la misma extensión de comportamiento, se producirá un error en tiempo de ejecución y también se registrará en el registro de eventos. También se deshabilita la ubicación de recepción.  
  
-   Los ensamblados a los que se hace referencia en la extensión de comportamiento personalizado deben estar presentes en la memoria caché global de ensamblados (GAC) antes de establecer las propiedades del controlador de adaptador.  
  
## <a name="configuring-the-adapter-handler-properties"></a>Configuración de las propiedades del controlador de adaptador  
 Use el procedimiento siguiente para configurar un controlador de recepción WCF-CustomIsolated.  
  
#### <a name="to-configure-the-adapter-handler-properties"></a>Para configurar las propiedades del controlador de adaptador  
  
1. En la consola de administración de BizTalk, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.  
  
2. En la lista de adaptadores expandida, haga clic en **WCF-CustomIsolated**, en el panel derecho, el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.  
  
3. En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que estará asociado, el controlador de recepción y, a continuación, Haga clic en **propiedades**.  
  
4. En el **propiedades de transporte WCF-CustomIsolated** cuadro de diálogo el **extensiones de WCF** ficha, realice lo siguiente:  
  
   |Use|Para|  
   |--------------|----------------|  
   |**Importar**|Importar un archivo de configuración de WCF con las extensiones de comportamiento personalizado de WCF. Al hacer clic en este botón abre el **importar configuración de WCF** cuadro de diálogo para examinar y buscar un archivo de configuración de WCF. Tenga en cuenta que el archivo debería ser un archivo de configuración de WCF válido. Para obtener más información acerca del esquema de configuración de WCF, vea "Esquema de configuración de Windows Communication Foundation" en [ http://go.microsoft.com/fwlink/?LinkId=163953 ](http://go.microsoft.com/fwlink/?LinkId=163953).|  
   |**Exportar**|Exportar la extensión de comportamiento personalizado de WCF a un archivo de configuración de WCF. Al hacer clic en este botón abre el **Exportar configuración de WCF** cuadro de diálogo para examinar y guardar el archivo de configuración de WCF.|  
   |**Desactivar**|Borrar la extensión de comportamiento personalizado de WCF existente de las propiedades del controlador de adaptador.|  
  
## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de WCF-CustomIsolated](../core/configuring-the-wcf-customisolated-adapter.md)