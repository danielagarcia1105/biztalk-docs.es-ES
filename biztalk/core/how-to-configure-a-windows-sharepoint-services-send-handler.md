---
title: Cómo configurar Windows SharePoint Services envían controlador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], send handlers
- send handlers, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, send handlers
ms.assetid: 457767d9-6e39-4553-9bbe-212fcb7c04bc
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90ac23759558549122f31a793852b479b67744d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988557"
---
# <a name="how-to-configure-a-windows-sharepoint-services-send-handler"></a>Cómo configurar un controlador de envío de Windows SharePoint Services
Siga el procedimiento siguiente para modificar el host al que está asociado el controlador de recepción de Windows SharePoint Services.  
  
> [!NOTE]
>  Cada host puede tener solo un controlador de envío asociado a él.  
  
### <a name="to-change-global-variables-for-a-windows-sharepoint-services-send-handler"></a>Para cambiar variables globales para un controlador de envío de Windows SharePoint Services.  
  
1. En la consola de administración de BizTalk Server, haga clic para expandir [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**y, a continuación, haga clic para expandir **grupo de BizTalk [\<servername\>:\< base de datos de administración\>]**, haga clic para expandir **configuración de plataforma**y, a continuación, haga clic para expandir **adaptadores**. La lista de adaptadores aparece debajo de la carpeta.  
  
2. Haga clic en **Windows SharePoint Services**y en el panel derecho, haga clic en el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.  
  
3. En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que se asociará el controlador de envío.  
  
4. En el **General** , haga clic **propiedades**.  
  
5. En el **propiedades de transporte Windows SharePoint Services** diálogo cuadro, realice lo siguiente:  
  
   |Use|Para|  
   |--------------|----------------|  
   |Tamaño del lote de envío|Número máximo de documentos que procesará el servicio Web del adaptador de mensajería de Windows SharePoint Services por lotes. El valor predeterminado es 20. **Nota:** el valor mínimo es 1.|  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar Windows SharePoint Services ubicación de recepción](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [Cómo configurar un puerto de envío de Windows SharePoint Services](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [Cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md)   
 [Referencia de propiedades de adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Expresiones del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-expressions.md)   
 [Tipos de columna admitidos de Windows SharePoint Services](../core/supported-windows-sharepoint-services-column-types.md)