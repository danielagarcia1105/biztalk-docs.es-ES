---
title: Cómo agregar metadatos de adaptador a un proyecto de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e439e5bf-94b3-4582-bacc-b058e6eb8e17
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c95cfac206dad58e0093945d2495c7e725c849c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968813"
---
# <a name="how-to-add-adapter-metadata-to-a-biztalk-project"></a>Cómo agregar metadatos de adaptador a un proyecto de BizTalk
El Asistente para agregar metadatos de adaptador le permite agregar metadatos de adaptador a un proyecto de BizTalk. Esos datos incluyen esquemas, tipos de mensajes y tipos de puertos necesarios para comunicarse con un adaptador desde una orquestación. Use este asistente con los adaptadores de aplicación, como FTP, para insertar los esquemas correspondientes a dichos adaptadores en el sistema. Tenga en cuenta que los adaptadores de transporte, como HTTP, no suelen usar esquemas.  
  
 El siguiente procedimiento le guiará por los pasos genéricos necesarios para agregar metadatos para un adaptador.  
  
### <a name="to-add-adapter-metadata-to-a-biztalk-project"></a>Para agregar metadatos de adaptador a un proyecto de BizTalk  
  
1. En su [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, en el Explorador de soluciones, haga clic en el proyecto, haga clic en **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
2. En el **agregar elementos generados - \<**  <em>nombre del proyecto</em> **\>** cuadro de diálogo el **plantillas** sección, Seleccione **agregar adaptador**y, a continuación, haga clic en **abierto**.  
  
3. En el Asistente para agregar metadatos de adaptador, en el **Seleccionar adaptador** página, realice lo siguiente.  
  
   |Use|Para|  
   |--------------|----------------|  
   |Cuadro Lista de adaptadores|Seleccione el adaptador registrado que desee agregar al proyecto.|  
   |SQL Server|Escriba el nombre del servidor de base de datos de BizTalk.|  
   |Base de datos|Muestra la lista de bases de datos de administración de BizTalk para el servidor elegido.|  
   |Puerto|Opcional. Muestra la lista de ubicaciones de recepción y puertos de envío de SQL que se han creado previamente y almacenado en la base de datos de administración de BizTalk. Solo se muestran los puertos configurados para funcionar con el adaptador seleccionado.|  
  
    Haga clic en **Siguiente**.  
  
   > [!NOTE]
   >  Al intentar agregar esquemas generados que contienen caracteres que el **System.XML.XMLConvert** clase no es compatible con los resultados en un error de compilación.  
  
4. Si está usando un adaptador estático, en el **seleccionar servicios para importar** , seleccione un conjunto de servicios disponibles desde la vista de árbol y, a continuación, haga clic en **finalizar**.  
  
    – O bien –  
  
    Si está usando un adaptador dinámico, siga los pasos de la interfaz de usuario personalizada para completar el asistente.  
  
   Una vez finalizado el asistente, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] muestra la lista de archivos .odx y .xsd en el Explorador de soluciones.