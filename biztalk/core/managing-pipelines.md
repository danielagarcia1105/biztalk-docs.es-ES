---
title: Administración de canalizaciones | Microsoft Docs
description: Vínculos rápidos para habilitar el seguimiento y las propiedades de canalización en un puerto de envío o ubicación de recepción en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60b54e0-0a5a-4264-b0e5-96bb187d782b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b15931468b5ba3bf43f227563dd270aabbfa29b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995261"
---
# <a name="managing-pipelines"></a>Administrar canalizaciones

## <a name="overview"></a>Información general
En esta sección se proporcionan instrucciones acerca del uso de la consola de administración de BizTalk Server para administrar las canalizaciones de un grupo de BizTalk. Puede configurar el seguimiento de eventos y mensajes, además de configurar propiedades de canalización para un puerto de envío o una ubicación de recepción concretos.  
  
 Las canalizaciones llevan a cabo acciones en mensajes entrantes y salientes, como transformarlos desde un formato nativo a XML, cifrar o descifrar datos, realizar la promoción de propiedades, etc.  
  
 No es posible agregar una canalización a una aplicación de manera individual; una canalización se agrega a una aplicación del modo que se especifica a continuación:  
  
- Cuando agrega un ensamblado de BizTalk que contiene una canalización a la aplicación, como se describe en [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).  
  
- Al importar un archivo .msi en una aplicación que incluye un ensamblado de BizTalk que contiene una canalización, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
- Cuando un programador implementa en una aplicación un ensamblado que contiene una canalización desde Visual Studio, como se describe en [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).  
  
  Para obtener información general acerca de las canalizaciones, consulte [canalizaciones](../core/pipelines.md). Para obtener información sobre el desarrollo de canalizaciones, consulte [crear canalizaciones utilizando Diseñador de canalizaciones](../core/creating-pipelines-using-pipeline-designer.md).  
  
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas. Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Configurar el seguimiento de una canalización](../core/how-to-configure-tracking-for-a-pipeline.md)  
  
-   [Configurar propiedades de canalización por instancia para un puerto de envío](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [Configurar propiedades de canalización por instancia para una ubicación de recepción](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)